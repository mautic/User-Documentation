.. vale off

Social Login
============

With Mautic's Social Login, users can easily sign in via their favorite social platforms like Twitter, Facebook, or LinkedIn. The social login feature automatically pre-fills forms with profile data and updates or creates new contacts in Mautic, streamlining the user experience.

Before You Begin: Setup Requirements
------------------------------------

Before enabling social login, make sure you have created social media apps on the platforms you want to integrate:

- `X-Developer <https://developer.twitter.com/en/portal/petition/essential/basic-info/>`_
- `Facebook <https://developers.facebook.com/products/facebook-login/>`_
- `LinkedIn <https://www.bing.com/ck/a?!&&p=b2b85466e898e3f3JmltdHM9MTcyODQzMjAwMCZpZ3VpZD0wZmNhOGE5ZC05ODA0LTY0OGYtMjVhYy05ZWQwOTk2MzY1NjYmaW5zaWQ9NTE5Mg&ptn=3&ver=2&hsh=3&fclid=0fca8a9d-9804-648f-25ac-9ed099636566&psq=linkedin+developer+app&u=a1aHR0cHM6Ly9kZXZlbG9wZXIubGlua2VkaW4uY29tLw&ntb=1>`_

Once these apps are set up, you're ready to connect them to Mautic!

Step 1: Authorizing Social Media Plugins
----------------------------------------

Before you can use social login, each social media plugin needs authorization. Here’s how to do it:

1. **Copy the Callback URL**: Go to Mautic's plugin configuration window and copy the Callback URL provided there. Paste it into the appropriate field in your social app setup.

 .. image:: images/Call_back.png
    :width: 400
    :alt: Screenshot of a call back url input field.

2. **Add Your API Keys**: Copy the API Key (Client Key) and API Secret (Client Secret) from the social platform. Paste these keys into the relevant fields in the Mautic plugin configuration.

.. image:: images/API_key.png
    :width: 400
    :alt: Screenshot of an API Key input field.

3. **Authorize the Plugin**: In the Mautic plugin configuration, click **Authorize**. Ensure the plugin is marked as **Published** by toggling the option to “Yes”. Finally, save your configuration to complete the setup.

.. Tip:: You can manage each social network under its respective tab in Mautic’s plugin settings. Make sure each network is fully authorized by adding the required API credentials.

Step 2: Adding Social Login Buttons to Forms
--------------------------------------------

Once your plugins are authorized, you can add social login buttons to your Mautic forms.

1. Go to the Forms section in Mautic and either create a new form or edit an existing one.

2. Select the **Social Login** field from the form builder. Buttons for all authorized social platforms (e.g., Twitter, Facebook, LinkedIn) will automatically appear.

3. When users log in using their social accounts, Mautic will attempt to automatically fill in fields like **Name** or **Email** based on their social profile.

.. image:: images/adding_social_login.png
   :alt: Mautic plugin configuration screen showing authorized status
   :width: 400

.. note:: 
   Only the buttons for plugins you’ve authorized will work in the form. Ensure all integrations are configured correctly for a smooth user experience.

Step 3: Configuring Features and Mapping Contact Fields
-------------------------------------------------------

Once the plugin is authorized, you can customize how Mautic handles the incoming social profile data. Under the **Contact Field Mapping** tab in the plugin settings, map the fields from the user’s social profile (e.g., Email, Name) to the appropriate Mautic contact fields.

- You only need to map fields that are relevant to your form.

- Unmapped fields will not be used to update or create contacts in Mautic.

Example: Map **First Name** from Facebook to **First Name** in Mautic's contact fields.

Supported Social Profile Fields
-------------------------------

Each platform provides different user data fields. Here's a quick reference of the fields you can map:

- **Twitter**: Profile Handle, Name, Location, Description, URL, Time Zone, Language, Email.

- **Facebook**: First Name, Last Name, Name, Gender, Locale, Email, Profile Link.

- **LinkedIn**: First Name, Last Name, Maiden Name, Formatted Name, Headline, Location, Summary, Specialties, Positions, Public Profile URL, Email Address.

.. vale on
