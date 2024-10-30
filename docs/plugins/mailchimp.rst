.. vale off

MailChimp
#########

.. vale on
This plugin can send contacts to MailChimp cilents based on Contact actions or Point Triggers.

Authorize
*********

 Get MailChimp API key
 ===========


1. Create a MailChimp account.
2. Go to *Account* / *Extras* / *API Keys* and create a new one.
3. Copy the created API Key.

 Authorize Mautic - MailChimp plugin
===========

1.Fill in with your MailChimp's account **username** 
2. Add the **API key**
3. Click on ***Save & Close***  

Configure the plugin
**********


Navigate to the *Features* tab in the plugin configuration modal box. You should see this note:

> The Contact Field Mapping tab will appear after selecting a segment and will update after changing the selected segment.

![MailChimp Plugin configuration](plugins-mailchimp-configure.png "MailChimp Plugin configuration")

1. Select the Segment.

   If you don't have a segment in [MailChimp][mailchimp] created yet, go to *MailChimp dashboard* / *Segments* / *Create List* and create one.

1. Save the plugin configuration
1. Open it again.

   The *Contact Field Mapping* tab should appear now.

1. Configure the [field mapping][field-mapping].

Other configuration options
===========


- **Push contacts to this integration**

   This option is checked by default. If you uncheck it, the plugin will not push contacts to MailChimp any more.

- **Enable double opt in** - If MailChimp should send a confirmation email to the contacts added by this plugin. The contacts will have to confirm that they really want to be added to the segment.
- **Send welcome email** - Whether MailChimp should send the welcome email.