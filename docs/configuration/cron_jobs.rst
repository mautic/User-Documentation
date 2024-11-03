.. vale off

Cron jobs
#########

.. vale on

.. attention::

    Mautic 3 introduced a new path for cron jobs ``bin/console`` - if you are using the legacy Mautic 2.x series you should replace this with the older version, ``app/console``

Mautic requires a few :xref:`cron jobs` to handle some maintenance tasks such as updating Contacts or Campaigns, executing Campaign Actions, sending Emails, and more. 
You must manually add the required cron jobs to your server. 
Most web hosts provide a means to add cron jobs either through SSH, cPanel, or another custom panel. 
Please consult your host's documentation/support if you are unsure on how to set up cron jobs.

If you're new to Linux or Cron Jobs, then the Apache Foundation has :xref:`an excellent guide` which you should read before asking questions via the various support Channels.

When setting up cron jobs, you must choose how often you want the cron jobs to run. Many shared hosts prefer that you run scripts every 15 or 30 minutes and may even override the scheduled times to meet these restrictions. Consult your host's documentation if they have such a restriction.

**It's HIGHLY recommended that you stagger the following required jobs so as to not run the exact same minute.**

For instance:

.. code-block:: 

    - 0,15,30,45 <— mautic:segments:update
    - 5,20,35,50 <— mautic:campaigns:update
    - 10,25,40,55 <— mautic:campaigns:trigger

Required
********

Mautic needs some mandatory cron jobs to run on a regular basis as follows:

Segment cron jobs
=================

**To keep the Segments current:**

.. code-block:: php

    php /path/to/mautic/bin/console mautic:segments:update

By default, the script processes Contacts in batches of 300. If this is too many for your server's resources, use the option ``--batch-limit=X`` replacing X with the number of Contacts to process each batch.

You can also limit the number of Contacts to process per script execution using ``--max-contacts`` to further limit resources used.

.. vale off

Campaign cron jobs
==================

.. vale on

**To keep Campaigns updated with applicable Contacts:**

.. code-block:: php

    php /path/to/mautic/bin/console mautic:campaigns:update

By default, the script processes Contacts in batches of 300. If this is too many for your server's resources, use the option ``--batch-limit=X`` replacing X with the number of Contacts to process each batch.

You can also limit the number of Contacts to process per script execution using ``--max-contacts`` to further limit resources used.

**To execute Campaigns events:**

.. code-block:: php

    php /path/to/mautic/bin/console mautic:campaigns:trigger

By default, the script processes Contacts in batches of 100. If this is too many for your server's resources, use the option ``--batch-limit=X`` replacing X with the number of events to process each batch.

You can also limit the number of Contacts to process per script execution using ``--max-events`` to further limit resources used.

Since Mautic 5.1, Mautic triggers Campaigns in order from newest to oldest. This allows you to process newer Campaigns with higher priority.

.. vale off

**To send frequency rules rescheduled marketing Campaign messages:** Messages marked as *Marketing Messages* - such as Emails as part of a marketing Campaign - get held in a message queue IF frequency rules are setup as either system wide or per Contact. To process this queue and reschedule sending these messages, add this cron job:

.. vale on

``mautic:messages:send``

.. note:: 

    that these messages are only added to the queue when frequency rules apply either system wide or per Contact.

.. vale off

Custom Field cron jobs
=======================

.. vale on

**To keep Contacts and Company Custom Fields updated**

.. code-block:: php

    php /path/to/mautic/bin/console mautic:custom-field:create-column

Optional
********

Depending on your server configuration, you can set up additional cron jobs that are optional for tasks such as sending Emails, importing Contacts, and more. The optional cron jobs are as follows:

.. vale off

Process Email queue cron job
============================

.. vale on

If the system configuration is queueing Emails, a cron job processes them.

.. code-block:: php

    php /path/to/mautic/bin/console messenger:consume email

.. vale off

Fetch and process Monitored Email cron job
==========================================

.. vale on

If you are using Bounce Management, set up the following command to fetch and process messages:

.. code-block:: php

    php /path/to/mautic/bin/console mautic:email:fetch

.. vale off 

Social Monitoring cron job
==========================

.. vale on

If you are using Social Monitoring, add the following command to your cron configuration:

.. code-block:: php

    php /path/to/mautic/bin/console mautic:social:monitoring

.. vale off

Import Contacts cron job
========================

.. vale on

To import an especially large number of Contacts or Companies in the background, use the following command:

.. code-block:: php

    php /path/to/mautic/bin/console mautic:import

The time taken for this command to execute depends on the number of Contacts in the CSV file. However, on successful completion of the import operation, a notification appears on the Mautic dashboard.

.. vale off

Export Contacts cron job
========================

.. vale on

To export Contacts to CSV - sending the results via Email - use the following command:

.. code-block:: bash

    php /path/to/mautic/bin/console mautic:contacts:scheduled_export

The time taken for this command to execute depends on the number of Contacts in the CSV file. However, on successful completion of the export operation, Mautic sends an email with the link to download the CSV.

Webhooks cron job
=================

If the Mautic configuration settings include Webhook batch processing, use the following command to send the payloads:

.. code-block:: php

    php /path/to/mautic/bin/console mautic:webhooks:process


Since Mautic 5.1 it's also possible to run the Webhooks cron job in 'range mode'. This allows you to specify a range of Webhook events to process in a single run. This can be useful if you have a large number of Webhook events to process and want to avoid running out of memory. 

To use this mode, you can specify the ``--min-id`` and ``--max-id`` options. For example, to process events for a Webhook with ID of 5, you can specify to only process the events for that Webhook with IDs between 1000 and 2000 using the following command:

.. code-block:: bash

    bin/console mautic:webhooks:process --webhook-id=5 --min-id=1000 --max-id=2000

.. _cron jobs:

.. vale off

Update MaxMind GeoLite2 IP database cron job
============================================

.. vale on

Mautic uses :xref:`MaxMind's` GeoLite2 IP database by default. 
The database license is :xref:`Creative Commons Attribution-ShareAlike 3.0 Unported License` and thus Mautic can't include it within the installation package. 
It's possible to download the database manually through Mautic's Configuration or automatically using the following script. MaxMind updates their database the first Tuesday of the month.


.. code-block:: php

    php /path/to/mautic/bin/console mautic:iplookup:download

Clean up old data cron job
==========================

Clean up a Mautic installation by purging old data. Note that you can't purge some types of data within Mautic. 
Currently supported are audit log entries, visitors - anonymous Contacts - and visitor Landing Page hits. Use ``--dry-run`` to view the number of records impacted before making any changes.

Use the ``--gdpr`` flag to delete data to fulfill GDPR European regulation. This deletes Contacts that have been inactive for 3 years.

**This permanently deletes data. Be sure to verify database backups before using as appropriate.**

.. code-block:: php

    php /path/to/mautic/bin/console mautic:maintenance:cleanup --days-old=365 --dry-run

MaxMind CCPA compliance cron job
================================

MaxMind requires Users to keep a "Do Not Sell" list up to date, and remove all data relating to those IP addresses in the past from MaxMind.

See more details in the official :xref:`MaxMind website`.

It's recommended to run these two commands once per week, one after another.

.. code-block:: php

    php /path/to/mautic/bin/console mautic:donotsell:download

This command downloads the database of Do Not Sell IP addresses from MaxMind.

.. code-block:: php

    php /path/to/mautic/bin/console mautic:max-mind:purge

This command finds data in the database loaded from MaxMind's Do Not Sell IP addresses and deletes the data.

.. vale off

Send scheduled broadcasts (Segment Emails) cron job
===================================================

.. vale on

Starting with Mautic 2.2.0, it's now possible to use cron to send scheduled broadcasts for Channel communications. The current only implementation of this is for Segment Emails. Instead of requiring a manual send and wait with the browser window open while AJAX batches over the send, it's possible to use a command to initiate the process.

The caveat for this is that the Email must have a published up date and be currently published - this is to help prevent any unintentional Email broadcasts. Just as it was with the manual/AJAX process the message is only sent to Contacts who haven't already received the specific communication. This command sends messages to Contacts added to the source Segments later, so if you don't want this to happen, set an unpublish date.

.. code-block:: php

    php /path/to/mautic/bin/console mautic:broadcasts:send [--id=ID] [--channel=CHANNEL]

Command parameters:
*******************

- ``--channel=email`` what Channel to execute. Defaults to all Channels if none provided.

- ``--id=X`` is what ID of Email, SMS or other entity to send.

- ``--limit=X`` is how many Contacts to pull from the database for processing, set to 100 by default. Using this flag each time the cron fires, it processes X Contacts. The next time the cron job runs, it processes the following X Contacts, and so on.

- ``--batch=X`` controls how many Emails processed in each batch. This can be different for every provider. For example, Mautic has API connection to SparkPost. Their API can send - at present - 1000 Emails per call. Therefore the batch should be 1000 for the fastest sending speed with this provider. Many SMTP providers can't handle 1000 emails in one batch, so this would need to be lower.

- ``--min-contact-id`` and ``--max-contact-id`` allows the separation of Email sending by smaller chunks, by specifying contact ID ranges. If those ranges won't overlap, this allows you to run several broadcast commands in parallel.

.. vale off

Send scheduled Reports cron job
===============================

.. vale on

Starting with Mautic 2.12.0, it's now possible to use cron to send scheduled Reports.

.. code-block:: php

    php /path/to/mautic/bin/console mautic:reports:scheduler [--report=ID]

.. note:: 

    for releases prior to 1.1.3, it's required to append ``--env=prod`` to the cron job command to ensure commands execute correctly.

.. vale off

Configure Mautic Integration cron jobs
======================================

.. vale on 

To perform synchronization of all Integrations and to manage Plugins, use the cron job commands in this section.

**To fetch Contacts from the Integration:**

.. code-block:: php

    php /path/to/mautic/bin/console mautic:integration:fetchleads

or 

.. code-block:: php

    php /path/to/mautic/bin/console mautic:integration:synccontacts

**To push Contact activity to an Integration:**

.. code-block:: php

    php /path/to/mautic/bin/console mautic:integration:pushactivity

or 

.. code-block:: php

    php /path/to/mautic/bin/console mautic:integration:pushleadactivity

These commands work with all available Plugins. To avoid performance issues when using multiple Integrations, you must specify the name of the Integration by adding the ``-integration`` suffix to the command. For instance, for integration of Mautic with HubSpot, use the following command:

.. code-block:: php

    php /path/to/mautic/bin/console mautic:integration:fetchleads --integration=Hubspot
    php /path/to/mautic/bin/console mautic:integration:pushactivity --integration=Hubspot

**To install, update, turn on or turn off Plugins:**

.. code-block:: php

    php /path/to/mautic/bin/console mautic:plugins:reload

.. note:: 

    you can replace ``mautic:plugins:reload`` with ``mautic:plugins:install`` or ``mautic:plugins:update``. 
    They're the same commands with different alias.

Exclude processed entities
**************************

This feature is particularly useful for managing data and ensuring that entities aren't processed multiple times unnecessarily. The ``--exclude`` option prevents the specified action from re-processing entities that it has already processed.. This option is available for the ``mautic:campaigns:trigger``, ``mautic:campaigns:rebuild``, and ``mautic:segments:update`` commands.

.. code-block:: php

    php /path/to/mautic/bin/console mautic:campaigns:trigger --exclude

.. note ::

    This is particularly useful for scenarios where you want to avoid redundant processing of entities, such as preventing a Campaign or Segment action from executing multiple times for the same Contact.

Tips & troubleshooting
**********************

If your environment provides a command-line specific build of PHP, often called ``php-cli``, you may want to use that instead of ``php`` as it has a cleaner output. On BlueHost and probably some other PHP hosts, the ``php`` command might be setup to discard the command-line parameters to ``console``, in which case you must use ``php-cli`` to make the cron jobs work.

To assist in troubleshooting cron issues, you can pipe the output of each cron job to a specific file by adding something like ``>>/path/to/somefile.log 2>&1`` at the end of the cron job, then you can look at the contents of the file to see the output.

If an error is occurring when running run the cron job this file provides some insight, otherwise the file is empty or has some basic stats. The modification time of the file informs you of the last time the cron job ran. You can thus use this to determine whether the cron job is running successfully and on schedule.

In addition it's recommended to enable the non-interactive mode together with the no-ansi mode when you run your commands using cron. This way you ensure, that you have proper timestamps in your log and the output is more readable.

Example output

.. code-block:: php

    php /path/to/mautic/bin/console mautic:segments:update --no-interaction --no-ansi
    [2016-09-08 06:13:57] Rebuilding contacts for segment 1
    [2016-09-08 06:13:57] 0 total contact(s) to be added in batches of 300
    [2016-09-08 06:13:57] 0 total contact(s) to be removed in batches of 300
    [2016-09-08 06:13:57] 0 contact(s) affected

If you have SSH access, try to run the command directly to Select for errors. If there is nothing printed from either in a SSH session or in the cron output, verify in the server's logs. If you see similar errors to ``'Warning: Invalid argument supplied for foreach()' in /vendor/symfony/console/Symfony/Component/Console/Input/ArgvInput.php:287``, you either need to use ``php-cli`` instead of ``php`` or try using ``php -d register_argc_argv=On``. `

