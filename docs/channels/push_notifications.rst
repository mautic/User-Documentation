Mobile push notifications
###########################

Mobile notifications integrate your iOS and Android app with :xref:`OneSignal`. Using your own OneSignal account, you can now push a notification to your Contact's mobile device - with their permission. Enable the Plugin in Mautic's Plugin manager to see Mobile Notifications listed under Channels in the menu.

For more detailed information see the :xref:`OneSignal iOS` and :xref:`OneSignal Android` documentation.

Setup
*****

.. vale off

iOS code for OneSignal integration
==================================

To enable Push Notifications in your iOS app, add the following code - or a variant of it - inside your ``application`` func of ``AppDelegate``. The code examples below use Swift 3.1. Please modify them to your needs if you are using C#.

.. code-block:: javascript

    // Somehow determine the user email. If you have user accounts, it may be better to move
    // this outside of the `application` func of `AppDelegate` in order to determine the user email.
    // In this example, the address is hardcoded for ease of use.
    let userEmail = "you@domain.com"

    OneSignal.initWithLaunchOptions(launchOptions, appId: "YOUR-ONE-SIGNAL-APP-ID")
    OneSignal.syncHashedEmail(userEmail);

    OneSignal.idsAvailable({(_ userId, _ pushToken) in
        let pushId      = userId != nil ? userId : ""
        let pushEnabled = pushToken != nil ? true : false
        let userData    = UserData(email: userEmail, push_id: pushId!, enabled: pushEnabled)

        self.pushUserDataToMautic(userData, "https://mautic.example.com/notification/appcallback")
    });

For ease of use, we've created the following struct and func for sending user data to Mautic. Create this struct in your app, and import it where appropriate.

UserData struct
~~~~~~~~~~~~~~~

.. code-block:: javascript

    struct UserData {
        var email   = String()
        var push_id = String()
        var enabled = Bool()

        static func toJSON(_ userData: UserData) -> String {
            let email   = userData.email
            let pushId  = userData.push_id
            let enabled = userData.enabled

            return "{\"email\":\"\(email)\",\"push_id\":\"\(pushId)\",\"enabled\":\(enabled)}"
        }
    }

pushUserDataToMautic func
~~~~~~~~~~~~~~~~~~~~~~~~~

This is a basic function for pushing the UserData struct to your Mautic installation. It will push the User data, and then display the response from Mautic as an app alert. Modify to meet the needs of your app.

.. code-block:: javascript

    func pushUserDataToMautic(_ userData: UserData, _ url: String) {
        var request = URLRequest(url: URL(string: url)!)
        request.httpMethod = "POST"

        let postString = UserData.toJSON(userData)
        request.httpBody = postString.data(using: .utf8)

        let task = URLSession.shared.dataTask(with: request) { data, response, error in
            guard let data = data, error == nil else {
                // check for fundamental networking error
                return
            }

            if let httpStatus = response as? HTTPURLResponse, httpStatus.statusCode != 200 {
                // check for http errors
                return
            }

            // Comment the next 4 lines to remove the alert 
            let responseString = String(data: data, encoding: .utf8)
            let alert = UIAlertController(title: "Response Data", message: responseString, preferredStyle: UIAlertControllerStyle.alert)
            alert.addAction(UIAlertAction(title: "OK", style: UIAlertActionStyle.default, handler: nil))
            self.window?.rootViewController?.present(alert, animated: true, completion: nil);
        }
        task.resume()
    }

.. vale on

Notification statistics
=======================

In addition to the UserData that gets pushed to Mautic, you can push open / interaction stats to Mautic by sending the UserData struct, with an appended stat JSON key.

