Troubleshooting a failed update 
###############################

Sometimes when updating Mautic, the process might stall or fail part way through. This can cause a problem, because it can cause Mautic to be in-between two versions and often this can make the system unusable.

.. note:: 
    Generally speaking, updates fail in this way because the hosting environment is inadequately resourced. Consider moving to a Virtual Private Server or Dedicated Server if you are using shared hosting. Read more in the :doc:`/getting_started/how_to_install_mautic` and :doc:`/getting_started/how_to_update_mautic` sections.

The following processes enables the completion of a failed upgrade.

Before you commence these steps, please ensure that you have a **tested backup of your Mautic instance** where possible.

Checking for schema updates
***************************

Mautic has a built-in tool which enables you to verify the database and identify if there are any schema updates required. Visit ``example.com/s/update/schema`` to see if there are any updates required.

If this isn't possible, or your Mautic instance is down completely, follow the next tips.

If you don't have SSH access, skip down to :ref:`SSH access isn't available`.

SSH access is available
***********************

Having SSH access to your server makes things much easier. Log in via command line, and change directory to the Mautic directory using the command:

.. code:: bash

    cd /your/mautic/directory

1. Try to clear the cache
=========================

When an upgrade attempt fails in the final step, it may be only the outdated cache that's causing a problem. Use the following command to clear it manually:

.. code:: bash

    php bin/console cache:clear

If this command throws a PHP error, you can try to remove the cache folder using the following command - be careful, this removes all files and folders in the path specified, so ensure you type it correctly, and in the correct directory.

.. code:: bash

    rm -rf var/cache

If clearing the cache hasn't resolved your problems, continue with the next step.

2. Trigger an update manually
=============================

The first step is to determine if there are any updates available using the following command:

.. code:: bash

    php bin/console mautic:update:find

The output from this command informs you if there are any updates to apply. If there are, run the following command to apply them:

.. code:: bash

    php bin/console mautic:update:apply

If there are no updates found, proceed to the next step.

3. Check for outstanding database migrations
============================================

Run the following command to identify any outstanding database migrations:

.. code:: bash

    php bin/console doctrine:migration:status

If there are any reported, firstly ensure that you have a tested backup of your database before proceeding, as this command causes changes to the database, then run:

.. code:: bash

    php bin/console doctrine:migration:migrate

4. Try to update the files manually
===================================

This step requires some manual intervention - there is no command for this part.

To update the files manually, you have to:

   1. Back up (download) all Mautic files from your server to your local computer, using File Transfer Protocol (FTP) or the ``scp`` command, which is much faster.
   2. Delete all Mautic files and folders on your server. Use FTP or the rm command - use the latter with extreme caution.
   3. Download the latest Mautic package from :xref:`Mautic Download`.
   4. Upload the zip package to the server, to the Mautic folder, using FTP or the ``scp`` command which is much faster.
   5. Unzip the package with ``unzip 3.3.3.zip`` -change the filename to match the one you have uploaded. You can then remove the zip file using the command ``rm 3.3.3.zip``.
   6. Upload ``config/local.php`` - note the location is ``app/config/local.php`` prior to Mautic 5.0 - from your backup on your local machine to the fresh Mautic folder on the server - Mautic should now run.
   7. Upload your custom data if you have some. You'll find custom files in the following folders: ``media/files``; ``plugins``; ``themes``; ``translations``.

SSH access isn't available
***************************

There is a PHP script which can do almost all steps from the section preceding. You can find this script :xref:`Troubleshooting PHP script`.

Below the script itself the description about how to use the script. There are some details you need to do differently, so please read these instructions carefully. For example, you must use FTP to upload and download the files. You must unzip the files on your local computer and upload those files, which takes a lot longer.

There is a PHP error when running a command
*******************************************

Firstly, read the error message which usually gives good indications to the problem. Next, search for the error in your preferred search engine. You can also search the :xref:`Mautic Community Forums` to see if others have reported and resolved the same problem.

Allowed memory size exhausted
=============================

This error reported is:

``PHP Fatal error:  Allowed memory size of 67108864 bytes exhausted (tried to allocate 10924085 bytes) in ...``

This means that the memory limit that Apache has available is too low. Edit the ``memory_limit`` in the ``php.ini`` configuration file. 

Read more about this in :doc:`/troubleshooting/working_with_resource_limits`.

A required PHP extension is missing
===================================

``Fatal: Class 'ZipArchive' not found``

This means that PHP can't work with Zip packages - you must make changes to your server configuration to allow unzipping of files at the command line. Ask your hosting provider, or search for a tutorial to help with this.

Need further help?
******************

If you need help, there are several places you can go to ask for assistance. Remember that most people who use the Community Forums, Chat, and GitHub are volunteers.

If you think your configuration is causing the problem, ask on the :xref:`Mautic Community Forums`. Search before you post, as it's likely someone might have already answered your question in the past.

You can also chat with someone in the live :xref:`Mautic Community Slack` however you must post all support requests must on the forums. Make a thread there first, then drop the link to the post in Slack if you are discussing it with someone.

In all cases, it's important that you describe the problem, and all steps you have followed to resolve the problem, in detail. At a minimum, include the following:

* Steps to reproduce your problem - a step-by-step tutorial of how the problem arose, or how to reproduce it
* The PHP version of your server
* The error messages you are seeing - if you don't see the error message directly, search for it in the var/logs folder and in the server log. Server logs are in different places depending on your setup. Ubuntu servers generally store their logs in ``/var/log/apache2/error.log``. Sometimes your hosting provider might offer a GUI to view logs in your Control Panel.

If you don't provide this information as a minimum, the person who might try to help you has to ask you for it, so please save them the trouble and provide the information upfront. Also, importantly, please be polite. Mautic is an Open Source project, and people are giving their free time to help you.

