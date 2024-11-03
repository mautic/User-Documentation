.. vale off

Twilio
######

Mautic - Twilio Plugin
======================

.. vale on

Before you start to send text messages from your Mautic instance, it needs to connect to the service which can send them.

The first and default implemented service is :xref:`Twilio`. 

In order to configure the text messages correctly, follow these steps:

1. Create an account at :xref:`Twilio`.

2. In Mautic, go to *Settings* (cog icon) > *Plugins*.

3. Open *Twilio* Plugin and activate it.

4. Log into your Twilio account and go to *Dashboard*.

 .. image:: images/twilio-sid-authtoken.png
    :width: 400
    :alt: Screenshot of the SID and Auth Token fields


5. Copy the *Account Sender ID (SID)* from Twilio account and paste it to *Account Sender ID* field in the Twilio Plugin configuration.

6. Unlock and copy the *Auth Token* and paste it to *Auth Token* field in the Twilio Plugin configuration.

7. Go to *Phone Numbers* > Active numbers in Twilio, add a phone number if you haven't already commissioned one.

8. Go to *Messaging* > *Services* in Twilio, and create a new Messaging Service. Select the appropriate settings from the dropdown in the first step as relevant to your usage of SMS messages with Mautic, then click 'Create Messaging Service' at the bottom right.

 .. image:: images/twilio-messaging-services.png
    :width: 400
    :alt: Screenshot of the Messaging Services interface

9. Click the button to add your phone number as a Sender for this Messaging Service, then select the box and click 'Set up Integration' at the bottom right to move on to the next step.

10. Select 'Send a Webhook' under the Integration settings.

11. Configure the Request URL and Fallback URL to use the callback URL of ``https://example.com/sms/twilio/callback`` where ``example.com`` is your Mautic instance domain. Also enter this in the 'Delivery Status Callback' field.

 .. image:: images/twilio-webhook-callback.png
    :width: 400
    :alt: Screenshot of the Messaging Services interface

12. Click the 'Add Compliance Info' button to proceed to the next step, where you can register to send Application to Person (A2P) messages using a 10 digit long code phone number. Otherwise, click the button in the bottom right to complete setup. Click on 'View my new Messaging Service' to see the details of the service you just created. Once created you can view the SID from the Messaging > Services screen.

 .. image:: images/twilio-messaging-service-id.png
    :width: 400
    :alt: Screenshot of the Messaging Services ID field on Twilio.

13. Copy the Messaging Service ID and paste this into the 'Features' tab of your Mautic Twilio Plugin settings

 .. image:: images/twilio-messaging-service-id-mautic.png
    :width: 400
    :alt: Screenshot of the Messaging Services ID field in Mautic.

14. Configure the global frequency rules for the SMS Channel as appropriate for your business.

15. Select the *Published*? switch to *Yes* in the Enabled/Auth tab in Mautic and save the Plugin configuration.

.. vale off

Alphanumeric Sender ID
======================

.. vale on

Alphanumeric Sender ID allows you to send SMS messages using a personalized sender name, in supported countries see :xref:`International Support for Alphanumeric Sender ID`.

Instead of using an E.164 formatted Twilio Phone number for the 'From' value, you can use a custom string like your own business' branding.

.. note:: 

     You can't reply directly to messages sent out with an Alphanumeric Sender ID.

.. vale off 

Alphanumeric Sender ID requirements
***********************************

.. vale on

Alphanumeric Sender ID is automatically supported on all new :xref:`upgraded (paid) Twilio accounts`. It's not supported for Free Trial accounts.

You can verify if your account has Alphanumeric Sender enabled by following these steps:

#. Login to your account at :xref:`Twilio`.

#. From the left side navigation bar, click Messaging > Overview.

#. Click Settings.

#. From the General Messaging Settings page, Verify the 'Alphanumeric Sender ID' setting.

 .. image:: images/twilio-alpha-numeric-number-settings.png
    :width: 400
    :alt: Screenshot of the Alphanumeric settings on Twilio.

.. vale off

Adding alphanumeric sender ID to a Messaging Service
====================================================

#. Open your Messaging Service via your Twilio Dashboard

#. Under the **Senders** section, click the **Add Senders IDs** button

#. From the **Add Senders IDs** dropdown, select **Alpha Sender** and enter the alphanumeric sender ID that you want to add to the Sender Pool.

Read more info about :xref:`Alphanumeric Sender ID` on Twilio site.