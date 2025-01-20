Assets
######

Assets are pieces of content you want to make available for your Contacts to access. You want to track and analyse  who is viewing or downloading your Assets. You also may want to personalize the Contact's journey based on what Assets they interacted with. You may also do scoring based on interaction with Assets.

.. vale off

Managing Assets
***************

Asset Categories
================

.. vale on

Mautic allows you to organize Assets into Categories, which helps you easily locate resources. To create a new Category, review the :doc:`/categories/categories-overview` documentation.

.. vale off

Working with Assets
===================

.. vale on

Before creating an Asset, first establish and create any Categories required. It's not possible to assign Assets to unavailable Categories. If you wish to use an Integration such as the Amazon S3 Plugin to host your files, set this up before creating an Asset.

.. vale off

Creating a new Asset
====================

.. vale on

Navigate to Components > Assets. Mautic lists any Assets you have previously created. Click New to begin creating an Asset.

You create Assets by uploading local resources on your computer, or by locating the Asset from a remote storage host such as Amazon S3. There are limitations by size due to the settings of your server - any such restriction may display as a warning message in the file upload section.

.. vale off

Add UTM codes to Asset
~~~~~~~~~~~~~~~~~~~~~~

.. vale on

UTM parameters appended to the download link means that UTM data is available in the resource download Report.

.. code-block:: php

``/asset/{id}:{name}?utm_source=test&utm_medium=test&utm_campaign=test&utm_id=test&utm_term=test&utm_content=test``


.. vale off

Uploading an Asset
~~~~~~~~~~~~~~~~~~

.. vale on

To upload an Asset, either drag the file into the box, or click in the box to open a file upload window. On selection of the file, it's automatically uploaded and appears in the boxed area.

By default Mautic allows the following file types:

.. code-block:: php

  csv,doc,docx,epub,gif,jpg,jpeg,mpg,mpeg,mp3,odt,odp,ods,pdf,png,ppt,pptx,tif,tiff,txt,xls,xlsx,wav

If you need to add extra file types, configure the maximum size of upload or the Assets directory, navigate to Configuration > Asset Settings.

.. image:: images/assets/asset_settings.png
  :width: 600
  :alt: Screenshot of Asset settings

The following fields are available:

- **Title** - the title for the Asset
- **Alias** - used to create the slug on the download URL. Created from the title automatically if not provided.
- **Description** - an internally used description to inform other Mautic Users what the Asset is and/or where it's used.
- **Category** - used to organize resources - see :doc:`/categories/categories-overview` for more information
- **Language** - the language of this Asset - can be helpful in multilingual marketing Campaigns and for reporting purposes
- **Available** - Whether the Asset is available for use or not available

.. vale off

**Activate at (date/time)** - This allows you to define the date and time at which this Asset is available

**Deactivate at (date/time)** - This allows you to define the date and time at which this Asset ceases to be available

.. vale on

- **Block search engines from indexing this file** - If you don't want to index files like ``PDF``, ``DOCx`` and so forth, setting this switch to Yes sends the ``X-Robots-Tag no-index`` HTTP header. If set to No, the header isn't sent and your files could become indexed by search engines.

Depending on the type of file uploaded, a preview may display after the upload completes.

.. image:: images/assets/asset_create.png
  :width: 600
  :alt: Screenshot of create new Asset interface

.. vale off

Using remote Assets
~~~~~~~~~~~~~~~~~~~

.. vale on

Instead of uploading a file from your computer, you can either provide a link to a file on a cloud storage provider or browse your integrated cloud storage provider - for example an Amazon S3 bucket - by selecting the Remote tab, rather than Local. 

.. vale off

Viewing an Asset
================

.. vale on

Once you've uploaded an Asset, you'll want to make it available for your Contacts to access it. Using the Download URL from the Asset section in Mautic, you can track which Contacts are downloading or viewing the Assets.

Copy and paste the link into your website, on a Landing Page, or as a link in an Email. 

.. note:: 
    In a Mautic Email or Landing Page, append ``?stream=1`` to the end of the URL to open the Asset in a new tab.

Whether the Asset downloads or opens in a new tab depends on the Contact's browser settings. To gate an Asset by requiring them to submit some information before downloading, you may have a Form submit action to download an Asset.

To ensure that Contacts are providing you with valid Email addresses for high-value Assets, attach the Asset to an Email and use the send Email Form submit action rather than instantly downloading the Asset.

.. vale off

Editing an Asset
================

.. vale on

You can edit an Asset by clicking on the 'edit' button while viewing the Asset, or by selecting the arrow next to the checkbox for the Asset, and selecting 'edit'. The edit screens are the same as the view screens,with the saved content already populated in the fields.

.. vale off

Deleting an Asset
=================

.. vale on

It's possible to delete an Asset by clicking on the 'delete' button while viewing the Asset, or by selecting the arrow next to the checkbox for the Asset, and selecting 'delete'. Mautic displays a confirmation screen, prompting confirmation that you wish to delete the Asset.

.. warning:: 
    Once deleted, you can't retrieve an Asset, and statistics relating to the number of downloads for that Asset are no longer be available. Contact Points accumulated as a result of accessing the resource remain. It's recommended where possible to deactivate Assets which are no longer in use - in future there may be an archive feature.

Display Assets directly in the browser
======================================

By default, Mautic supports the following file types for direct display in the browser:

.. vale off

- gif
- jpg
- jpeg
- mpg
- mpeg
- mp3
- pdf
- png
- wav

.. vale on

If you want to change this default behavior, you can modify the ``local.php`` file and set an array of extensions for the ``streamed_extensions`` parameter.
