Working with resource limits
############################

You may come across limitations with your server configuration when installing or using Mautic. These commonly manifest as errors such as:

.. code:: bash

    The Uploaded file exceeds the upload_max_filesize directive
    Maximum execution time of 30 seconds exceeded - in file <filepath> - at line <line number> 
    PHP Error: Allowed memory size of <number> bytes exhausted (tried to allocate <number> bytes) - in file <filepath> - at line <number>

These are, in general, not errors with Mautic, but with your server configuration. To resolve these issues you need to make some changes to your server configuration.

Resolving issues
****************

To resolve these problems you require: 

* Access to your server to change configuration files - generally via SSH - or; 
* Access to your hosting provider's Control Panel, which may allow you to change these settings via the User Interface * Access to a text editor such as ``Nano`` or ``Vi``

.. note:: 
    Note: Nano is used in this walk through, if you don't use Nano simply replace 'nano' with the name of the editor you prefer to use. See this :xref:`Nano keyboard commands` cheat sheet for a useful keyboard shortcut guide when using Nano.

Find the ``php.ini`` file loaded
********************************

The first step is to find which ``php.ini`` file in use. The :xref:`php.ini file` is a configuration file which controls how PHP functions.

You have access to Mautic
=========================

If you have access to your Mautic instance, navigate to Settings > System Info > PHP Info where you can view a file which tells you every configuration setting for PHP that Mautic is using. In particular, the areas outlined in red in the screenshot below give you the paths to the relevant files.

.. image:: images/phpini-settings.png
    :width: 400
    :alt: Screenshot of PHP settings in Mautic dashboard

A note on local versus master values
------------------------------------

When you view the PHP info file, there are two values, ``Master`` and ``Local``.

Master value
~~~~~~~~~~~~

This comes from your main ``php.ini`` file - the one loaded in the preceding section. This is the value which applies server-wide.

Local value
~~~~~~~~~~~

The global setting can be overridden locally in multiple locations, such as ``httpd.conf``, ``.htaccess`` or other Apache configuration.

This is often used to get around restrictive settings at the server level, and can sometimes mean that making changes at the top global level doesn't trickle down to your specific folder or location. So if you have a discrepancy between the two, look for a local ``.htaccess`` or a ``*.ini`` file within your Mautic directory, or verify with your hosting provider.

You don't have access to Mautic
===============================

If you can't access the System Info of Mautic, you can verify the path for ``php.ini`` using a command:

.. code:: bash

    php -i | grep .ini

You can also use the same command to find the specific value used:

.. code:: bash
    
    php -i | grep upload_max_filesize

where ``upload_max_filesize`` is the value you need to change.

Updating the value
------------------

Once you have located the ``php.ini`` file in use, you should be able to edit it using the following command:

.. code:: bash
    
    sudo nano path/to/file/php.ini

Find the relevant setting using ``ctrl+w`` - keyboard shortcut for 'where' - and then typing the setting you need to change - for example ``upload_max_filesize``.

Change the value you see in the ``php.ini`` file, and then save, using ``ctrl+x`` - keyboard shortcut for 'exit' and then pressing ``y`` to save changes.

.. vale off

Restarting Apache
-----------------

.. vale on

Once you've saved the changes, you need to restart Apache for the changes to take effect.

It's always a good idea to do a dry-run first, using the :xref:`Apache configtest` command

.. code:: bash
    
    sudo apachectl configtest

This checks that your Apache configuration is sound before you restart the service. Resolve any issues identified before restarting Apache.

Once you are happy, run the following command to restart Apache:

.. vale off

Ubuntu and Debian
~~~~~~~~~~~~~~~~~

.. vale on

.. code:: bash
    
    sudo systemctl restart apache2

.. vale off

CentOS and Red Hat
~~~~~~~~~~~~~~~~~~

.. vale on

.. code:: bash
    
    sudo systemctl restart httpd

Overriding the value
--------------------

If you aren't able to change the value at the ``php.ini`` level, it may be possible - dependant on your server configuration - to override the value at the local folder level.

Check out this :xref:`PHP config changes` article for more details on how to override the ``php.ini`` settings with a local ``.htaccess`` file.

As an example of two settings you may wish to use in a local htaccess file to override the values in the global ``php.ini`` file:

.. code:: bash
    
    php_value upload_max_filesize 20M
    php_value max_execution_time 600

This is a last resort, and your hosting provider may not support it.


