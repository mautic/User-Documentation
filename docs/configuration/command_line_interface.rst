.. vale off

Command Line Interface (CLI) commands
#####################################

.. vale on

Mautic may require you to use the command line (CLI). Listed below are the available CLI commands.

.. note:: 

  You can find this list (and others - for example commands relating to Doctrine and other vendors) by running this command: ``bin/console``

  You must be in the Mautic root directory to run the CLI commands. 

**Format**: command [options] [arguments]

Options
=======

.. vale off

.. list-table:: 
   :widths: 50 50
   :header-rows: 1

   * - Options
     - Description
   * - -h, \--help
     - Display this help message
   * - -q, \--quiet
     - Do not output any message
   * - | V, \--version
       |  \--ansi
       |  \--no-ansi
     - | Display this app version
       | Force ANSI output
       | Disable ANSI output
   * - -n, \--no-interaction
     - 	Do not ask any interactive question
   * - | -s, \--shell
       |  \--process-isolation
     - | Launch the shell.
       | Launch commands from shell as a separate process.
   * - | -e, \--env=ENV
       |  \--no-debug
     - | The Environment name. [default: "prod"]
       |  Switches off debug mode.
   * - | -v
       | -vv
       | -vvv
       |  \--verbose
     - | Increase the verbosity of messages:
       | 1. for normal output,
       | 2. for more verbose output and
       | 3. for debug

       
.. vale on

Mautic commands
===============
These are the commands you may need to use in relation to your Mautic instance. Add a ``bin/console`` before Mautic command.

**Example**

.. code-block:: shell

  bin/console mautic:segments:update

.. vale off

.. list-table:: 
   :widths: 25 50 25
   :header-rows: 1

   * - Command
     - Description
     - Aliases
   * - ``mautic:assets:generate``
     - Combines and minifies Asset files (CSS/JS) from each bundle into single production files
     - 
   * - ``mautic:broadcasts:send``
     - Process Contacts pending to receive a Channel broadcast.
     - 
   * - ``mautic:campaigns:execute``
     - Execute specific scheduled events.
     - 
   * - ``mautic:campaigns:rebuild``
     - Rebuild Campaigns based on Contact Segments.
     - ``mautic:campaigns:update``
   * - ``mautic:campaigns:trigger``
     - Trigger timed events for active Campaigns.
     - 
   * - ``mautic:campaigns:validate``
     - Validate if a Contact has been inactive for a decision and execute events if so.
     - 
   * - ``mautic:citrix:sync``
     - Synchronizes registrant information from Citrix products
     - 
   * - ``mautic:cache:clear``
     - Clears Mautic cache, by using this command, you will erase the 10-minute Mautic cache, which contains things like segment counts and data for dashboard widgets.
     - 
   * - ``mautic:contacts:deduplicate``
     - Merge Contacts based on same unique identifiers
     - 
   * - ``mautic:contacts:scheduled_export``
     - Processes exports of Contacts to a CSV file and sends the results via Email.
     -
   * - ``mautic:custom-field:create-column``
     - Creates the actual column in the table
     - 
   * - ``mautic:email:fetch``
     - Fetch and process monitored Email.
     - 
   * - ``messenger:consume email``
     - Processes mail queue
     - 
   * - ``mautic:fields:analse``
     - Analyze Custom Fields table and return table or file with results. See :doc:`/contacts/custom_fields`.
     - 
   * - ``mautic:import``
     - If the CSV import is configured to run in background then this command will pick up the pending import jobs and imports the data from CSV files to Mautic.
     - 
   * - ``mautic:integration:fetchleads``
     - Fetch Contacts from Integration.
     - ``mautic:integration:synccontacts``
   * - ``mautic:integration:pipedrive:fetch``
     - Pulls the data from Pipedrive and sends it to Mautic
     - 
   * - ``mautic:integration:pipedrive:push``
     - 	Pushes the data from Mautic to Pipedrive
     - 
   * - ``mautic:integration:pushleadactivity``
     - Push Contact activity to Integration. 
     - ``mautic:integration:pushactivity``
   * - ``mautic:install:data``
     - Installs data
     - 
   * - ``mautic:iplookup:download``
     - Fetch remote datastores for IP lookup services that leverage local lookups.
     - 
   * - ``mautic:maintenance:cleanup``
     - Cleans up older data.
     - 
   * - ``mautic:messages:send``
     - Process sending of messages queue.
     - ``mautic:campaigns:messagequeue``, ``mautic:campaigns:messages``
   * - ``doctrine:migrations:generate``
     - Generate a blank migration class.
     - 
   * - ``mautic:plugins:reload``
     - Install, reloads or updates Plugins.
     - ``mautic:plugins:install``, ``mautic:plugins:update``
   * - ``mautic:queue:process``
     - Process queues
     - 
   * - ``mautic:reports:scheduler``
     - Processes scheduler for Report's export
     - 
   * - ``mautic:segments:update``
     - Update Contacts in smart Segments based on new Contact data.
     - ``mautic:segments:rebuild``
   * - ``mautic:theme:json-config``
     - Converts Theme config to JSON from PHP
     - 
   * - ``mautic:unusedip:delete``
     - Deletes IP addresses that aren't used in any other database table
     - 
   * - ``mautic:update:apply``
     - Updates the Mautic app.
     - 
   * - ``mautic:update:find``
     - Fetches updates for Mautic
     - 
   * - ``mautic:webhooks:process``
     - Process queued Webhook payloads
     - 
   * - ``social:monitor:twitter:hashtags``
     - Looks at the monitoring records and finds hashtags.
     - 
   * - ``social:monitor:twitter:mentions``
     - Searches for mentioned tweets
     - 

.. vale on

Doctrine commands
=================

.. list-table:: 
   :widths: 50 50
   :header-rows: 1

   * - Command
     - Description
   * - ``doctrine:fixtures:load``
     - Installs Mautic sample data, overwriting existing data.
