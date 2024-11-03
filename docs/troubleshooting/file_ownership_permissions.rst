File ownership and permissions
##############################

If you experience errors like the following:

.. code:: bash
    
    .WARNING: PHP Warning - require(/mautic/var/cache/prod/doctrine/orm/Proxies/__CG__MauticCategoryBundleEntityCategory.php): failed to open stream: No such file or directory - in file /mautic/vendor/doctrine/common/lib/Doctrine/Common/Proxy/AbstractProxyFactory.php - at line 209

there is a strong likelihood that you have problems with the permissions and/or ownership of the files and folders on your Mautic instance.

This article writes from the perspective of a Linux server using Apache, which is the most common hosting environment for Mautic. NGINX and IIS servers have different configurations, but the principles remain the same.

Why are permissions important?
******************************

File and folder permissions specify who and what can read, write, modify, and access them. Ownership determines which User 'owns' the files and folders - and hence is able to carry out actions based on the permission settings.

User
====
A User is the owner of the file. By default, the person who created a file becomes its owner. Hence, a User is also sometimes called an **owner**.

Group
=====
A Group can contain multiple Users. All Users belonging to a Group have the same access permissions to the file. Groups simplify permissions - all Users in a specific Group inherit the permissions assigned to that Group, rather than having to assign permissions to each User individually.

Other
=====
Any other User who has access to a file comes into 'Other', meaning they have neither created the file, nor belong to a Group that owns the file. Practically, this means 'the rest of the world'. Hence, this is also referred to as **permissions for the world**.

Linux distinguishes between these three User types to prevent Users accessing, editing, or deleting files they shouldn't be able to change. Read more about :xref:`Linux file and folder ownership documentation`

Permissions and ownership settings are critical to ensuring the security of your server and Mautic instance, so it's important to get them right. If your files don't have the appropriate permissions in place, it's easier for hackers to intrude on your files and gain access to your Mautic instance. Setting your file permissions correctly may not save you from all attacks, but it helps make your Mautic instance a bit more secure.

Why do permissions problems cause errors in Mautic?
***************************************************

Mautic needs access to read and write files in the Mautic directory to enable certain functions and scripts to run. If the permissions aren't set correctly, or if the User running them doesn't have the correct access, Mautic can't function properly and errors occur in the app and server logs as a result.

Problems with permissions and ownership generally occur because:

* You've uploaded Mautic or made changes to files and folders as a different User to the one that Mautic uses to run - for example you uploaded files using an FTP account with the username ``bob`` but your web server executes scripts as a User called ``www-data``.
* The User that Mautic uses to run doesn't have the appropriate permissions on the files and folders - for example, ``bob`` isn't able to create directories, or read files
* You ran an update as a different User to that which Mautic uses to run - resulting in some files and folders having their ownership changed

How to fix permission-related problems in Mautic
************************************************

Resetting the permissions of your files and folders requires running some commands at the command line. You need to have SSH access to your server, or ask someone who does to execute these commands for you. Some hosting providers may be able to create a script to periodically reset permissions if this becomes an ongoing problem for you.

Solution for hosting providers that offer cPanel access
=======================================================
A script to fix permissions & ownership, on files & directories, for cPanel accounts. You could ask your hosting provider to run that script to reset the permissions to the correct values. Find this handy script here: :xref:`cPanel fix permissions script`.

Identifying the problem
=======================
Log into your server using SSH, and change to the Mautic directory using the command

.. code:: bash
    
    cd path/to/mautic

In this directory, execute the following command:

.. code:: bash
    
    ls -l

The ``ls`` command lists files and directories. It has an option of ``-l``, which lists the contents in a long format, including their permissions and ownership amongst other information.

For a more detailed explanation of what all the information means, take a look at this article: :xref:`Linux ls command`.

The key information is in the first, third, and fourth columns - the permissions, and the User and Group owning the files/folders.

Reset the file and folder permissions
=====================================

If your file and folder permissions are incorrect, you can run the following commands to reset them:

.. code-block:: bash

    find . -type f -not -perm 644 -exec chmod 644 {} +
    find . -type d -not -perm 755 -exec chmod 755 {} +
    chmod -R g+w var/cache/ var/logs/ app/config/
    chmod -R g+w media/files/ media/images/ translations/
    rm -rf var/cache/*

Change ownership of files and folders
=====================================

Errors can continue if there is a problem with ownership of your files and folders, even with the correct file and folder permissions. This is because the User may not have the necessary permission - as they're not the owner of the files/folders. Read more about :xref:`Linux file and folder ownership documentation`.

To find out which User Apache is running as, run the following command and take note of the first entry in the line returned:

.. code:: bash
    
    ps aux | grep apache2

Use this information to find the Groups with the following command

.. code:: bash
    
    groups apache_user - where apache_user is the user you identified from the first step above

To reset the ownership of files and folders, use the following command - ensuring that you replace ``apache_user`` and ``apache_group`` with the values identified in the preceding steps:

.. code:: bash
    
    sudo chown -R apache_user:apache_group /path/to/mautic

.. vale off

This command **ch-** anges **own-** ership, using the ``-R`` flag which means recursively - including all files/folders within that location. Read more about the :xref:`Linux chown command`.

.. vale on
