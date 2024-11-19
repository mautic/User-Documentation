
Social login
############

With Mautic's Social Login, Users can easily sign in via their favorite social platforms like Twitter, Facebook, or LinkedIn. The social login feature automatically pre-fills Forms with profile data and updates or creates new Contacts in Mautic, streamlining the user experience.

Before you begin: setup requirements
************************************

Before configuring social login, make sure you have created apps on the developer platforms for the social media profiles you want to integrate:

- :xref:`X-developer`
- :xref:`Facebook developer`
- :xref:`LinkedIn developer`

Once created, you're ready to connect them to Mautic.

Step 1 - authorizing social media Plugins
*****************************************

Before you can use social login, each social media Plugin needs authorization. Here's how to do it:

1. **Copy the Callback URL**: go to Mautic's Plugin configuration window and copy the Callback URL provided there. Paste it into the appropriate field in your developer app setup.

 .. image:: images/Call_back.png
    :width: 400
    :alt: Screenshot of a callback URL input field.

2. **Add Your API Keys**: copy the API Key - Client Key - and API Secret - Client Secret - from the social platform. Paste these keys into the relevant fields in the Mautic Plugin configuration.```

.. image:: images/API_key.png
    :width: 400
    :alt: Screenshot of an API Key input field.

1. **Authorize the Plugin**: in the Mautic Plugin configuration, click **Authorize**. You must **turn on** the Plugin - do this by toggling the option to “Yes”. Finally, save your configuration to complete the setup.

.. Tip:: You can manage each social network under its respective tab in Mautic's Plugin settings. Make sure each network is fully authorized by adding the required API credentials.

Step 2: adding social login buttons to Forms
********************************************

Having configured the social Plugins, you can add social login buttons to your Mautic Forms.

1. Go to the Forms section in Mautic and either create a new Form or edit an existing one.

2. Select the **Social Login** field from the Form builder. Buttons for all authorized social platforms - for example Twitter, Facebook, LinkedIn automatically appear.

3. When Users log in using their social accounts, Mautic attempts to automatically fill in fields like **Name** or **Email** based on their social profile.

.. image:: images/adding_social_login.png
   :alt: Mautic Plugin configuration screen showing authorized status
   :width: 400

.. note:: 
   Only the buttons for Plugins you've authorized work in the Form. Ensure you've configured all Integrations correctly for a smooth User experience.

Step 3: configuring features and mapping Contact fields```
*******************************************************

After configuration and authorization of the Plugin, you can customize how Mautic handles the incoming social profile data. Under the **Contact Field Mapping** tab in the Plugin settings, map the fields from the User's social profile - for example Email, Name - to the appropriate Mautic Contact fields.

- You only need to map fields that are relevant to your Form.

- Unmapped fields aren't used to update or create Contacts in Mautic.

Example: map **First Name** from Facebook to **First Name** in Mautic's Contact fields.

Supported social profile fields
*******************************

Each platform provides different user data fields. Here's a quick reference of the fields you can map:

- **Twitter**: profile handle, name, location, description, URL, time zone, language, email address.

- **Facebook**: first name, last name, name, gender, locale, email address, profile link.

- **LinkedIn**: first name, last name, maiden name, formatted name, headline, location, summary, specialties, positions, public profile URL, email address.

