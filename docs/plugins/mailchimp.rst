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
   
.. image:: plugins-mailchimp-create-api-key-1-and-2.png
  :alt: Screenshot of MailChimp dashboard with arrows pointing at the Extras tab and the API Keys section
  :align: center

  .. image:: plugins-mailchimp-create-api-key-3a.png
   :alt: Screenshot of MailChimp dashboard with an arrow pointing at the Create API Key button
   :align: center

   .. image:: plugins-mailchimp-create-api-key-3b-and-3c.png
      :alt: Screenshot of the Name New API Key section with arrows pointing at the test and Generate Key button
      :align: center

 Authorize Mautic - MailChimp plugin
===========

1. Fill in with your MailChimp's account **username** 
2. Add the **API key**
3. Click on ***Save & Close***  



Configure the plugin
**********


Navigate to the *Features* tab in the plugin configuration modal box. You should see this note:

> The Contact Field Mapping tab will appear after selecting a segment and will update after changing the selected segment.

.. image:: plugins-mailchimp-configure.png
   :alt: MailChimp Plugin configuration
   :align: center

1. Select the Segment.

   If you don't have a segment in [MailChimp][mailchimp] created yet, go to *MailChimp dashboard* / *Segments* / *Create List* and create one.

2. Save the plugin configuration
3. Open it again.

   The *Contact Field Mapping* tab should appear now.

4. Configure the [field mapping][field-mapping].

Other configuration options
===========


- **Push contacts to this integration**

   This option is checked by default. If you uncheck it, the plugin will not push contacts to MailChimp any more.

- **Enable double opt in** - If MailChimp should send a confirmation email to the contacts added by this plugin. The contacts will have to confirm that they really want to be added to the segment.
- **Send welcome email** - Whether MailChimp should send the welcome email.