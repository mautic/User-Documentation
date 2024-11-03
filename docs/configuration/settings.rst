Mautic configuration settings
#############################

Proper configuration is important for branding, performance, and the User experience for your team as they do their jobs. 
These settings mostly don't need changing after initial configuration.

System settings
***************

General settings
================

.. image:: images/general-settings.png
  :width: 600
  :alt: Screenshot showing General Settings Configuration in Mautic

* **Site URL** - This is where Mautic is physically installed. Set the URL for this site here. Cron jobs needs this to correctly determine absolute URLs when generating links for Emails, etc. It 's also called Mautic's 'base URL'.

* **Mautic's root URL** - When a User signs in to their Mautic instance, they go to ``mautic.example.com``. However, that Landing Page is also accessible to the public. If a Contact visits that address, they see the Mautic login page for that instance.

  To brand that Landing Page, create a Mautic Landing Page that you'd want to greet any Contacts who visit your root ``URL``. Once you've done that, Users can sign in into Mautic by visiting ``mautic.example.com/s/login``.

* **404 page** - Select the Landing Page that you want to use as the 404 Landing Page. If you don't want to use Mautic's default 404 error page, create a custom Landing Page and select that Landing Page here. If you don't select any page, Mautic uses the default error page.


* **Path to the cache, log, and images directory** - These are the file system paths where Mautic saves the cache, logs, and images.

System defaults
===============

.. image:: images/system-default-settings.png
  :width: 600
  :alt: Screenshot showing System defaults Settings Configuration in Mautic

* **Default item limit per page** - The number of Contacts, Campaigns, Emails, etc. which display on each page when you go to an item section. The default is ``10``.

* **Default timezone** - The User's default time zone, typically set to the time zone of the Company headquarters. Mautic allows the User to set their own time zones via their profile. The default is ``UTC``.

  For example: headquarters is in Boston and Mautic's timezone is ``America/New York``. A User in San Francisco which is Pacific Time may set ``America/Los Angeles`` to use Pacific Time in the User interface.

* **Default language** - The initial language assigned to Users. Individual Users may select their own settings. Mautic uses ``English - United States`` by default.

* **Cached data timeout (minutes)** - Mautic caches data to speed up page loads. Update this setting to change how long Mautic caches the data for. Mautic uses ``10 minutes`` as the default.

* **Date Range Filter Default** - Sets the default for how far back from the current date Mautic looks for data in Reports including Campaign and Email snapshots charts on the item page. This setting allows you to control the default for how far back from the current date Mautic looks for data. If you've changed the setting on a Report, Mautic uses what you've entered. Mautic's default value is ``1 Month``.
   
* **Default format for full dates, date only, short dates, and time only** - The default setting uses the standard American time format. The letters in the boxes are PHP code. See the :xref:`PHP manual for date functions`.

CORS settings
=============

Cross-Origin Resource Sharing - CORS - allows data to pass between your website and Mautic.

.. image:: images/cors-settings.png
  :width: 600
  :alt: Screenshot showing CORS Settings Configuration in Mautic

* **Restrict Domains** - When set to No, any website can pass information to Mautic. Selecting ``Yes`` to limit communication with your Mautic instance to websites listed in Valid Domains is **strongly recommended**.

* **Valid Domains** - A list of domains allowed to communicate with your Mautic instance. In the text box, list the exact URL of the top level domain you want to allow, one per line. For example: ``http://www.example.com`` tracks any activity on non-secure example.com pages, but ``https://www.example.com`` won't because this is only tracking on a secure ``https://`` website.

.. note:: 

  In the Valid Domains field, don't include a slash at the end. For example, use ``https://www.example.com`` instead of ``https://www.example.com/``.

Miscellaneous settings
======================

.. image:: images/miscellaneous-settings.png
  :width: 600
  :alt: Screenshot showing Miscellaneous Settings Configuration in Mautic

* **Trusted hosts** - To explicitly allow the hosts that can send requests to Mautic. You can use regular expression and separate multiple hosts with a comma. i.e ``.*\.?example.com$``. If left empty, Mautic will respond to all hosts.
  
* **Trusted proxies** - To configure the IP addresses that Mautic should trust as proxies. This setting is mandatory when using Mautic behind an SSL terminating proxy. Separate multiple IP addresses by a comma. i.e ``127.0.0.1, 10.0.0.0/8, fc00::/7``

* **IP lookup service** - By default, Mautic uses :xref:`MaxMind's` database to identify the city of a website visitor, based on the location of the Internet Service Provider - ISP - for their IP address.

* **IP lookup service authentication** - To use any IP lookup service which requires authentication, enter your credentials.
  
* **List of IPs not to track Contacts with** - To turn off tracking for particular IP addresses, enter the addresses, one per line. Mautic doesn't recommend adding your office IP address. If you list your internal IP address, Mautic won't track clicks, page hits, etc., from that IP, **including when you are testing** which can cause difficulties.

* **List of known Bots** - Mautic has the feature to identify and turn-off tracking for several known bots. To track activity from those bots, remove them from this list. To turn off tracking for other bots, add them here - one per line.
  
* **URL Shortener** - If you use a URL shortening service like bit.ly for links in SMS messages, enter your access token here.

.. note:: 

    For bit.ly, use the following URL structure: ``https://api-ssl.bitly.com/v3/shorten?access_token=[ACCESS_TOKEN]&format=txt&longUrl``

* **Item max lock time** - When a User edits a Campaign, Email, Landing Page, etc., Mautic locks the item to prevent simultaneous edits by other Users. When the initial User saves and closes or cancels out, the item may remain locked for this period of time. The default is ``0 seconds``.

* **Translate page titles** - To translate page titles in the Contact activity history from non-Latin characters to Latin - English - characters.


Update settings
===============

.. image:: images/update-settings.png
  :width: 600
  :alt: Screenshot showing Update Settings Configuration in Mautic

* **Set the minimum stability level required for updates** - This allows you to receive notifications for early access releases. Always read the release notes before updating to an early access release. Set the minimum stability level required for updates. 

* **Update Mautic through Composer [beta]**  - Set to 'Yes' if you update Mautic through Composer. This is a prerequisite if you want to install and update Plugins through the Marketplace. This becomes the default installation and update method in Mautic 5.

Theme settings
**************

.. image:: images/theme-settings.png
  :width: 600
  :alt: Screenshot showing Theme Settings Configuration in Mautic

* **Default Theme** - Applies a Theme to any Form which doesn't have a Theme already applied. If you don't have a Landing Page for your Preference Center, but have preference settings turned on in Email settings, Mautic creates a default Preference Center page using the Form styling from the Theme selected here.

API settings
************

.. image:: images/api-settings.png
  :width: 600
  :alt: Screenshot showing API Settings Configuration in Mautic

Full API documentation is available :xref:`Mautic developer API`.

* **API enabled** - Select Yes to pass data in and out of Mautic through the API.

* **Enable http basic auth?** - Enables basic authentication for Mautic's API. It's recommended to only use this with secure sites (https).

* **Access token lifetime** - When authorizing a new app or Integration, this setting limits how long the access token is valid - in minutes. The default is ``60`` minutes.

  For example - You add a new Integration to your SaaS platform. Enter 30 here to limit the access token validity to ``30`` minutes. If you haven't completed the authentication in that period of time, you must revalidate.

* **Refresh token lifetime** - When using OAuth 2.0, the lifetime of the refresh token used to request a new access token once expired. Once the refresh token expires, you must reauthorize. The default is ``14`` days.

Asset settings
**************

.. image:: images/assets-settings.png
  :width: 600
  :alt: Screenshot showing Assets Settings Configuration in Mautic

* **Path to the Asset directory** - Set the absolute path to the Assets upload folder. In order to prevent the public from accessing Assets, use a directory outside of the public web root.

* **Maximum size Megabytes** - Set the maximum size of uploaded Assets in Megabytes.

* **Allowed file extensions** - Extensions of files separated by commas. You can only upload files with the specified file extensions.

Campaign settings
*****************

.. image:: images/campaign-settings.png
  :width: 600
  :alt: Screenshot showing Campaign Settings Configuration in Mautic

* **Wait time before retrying a failed action** - If for any reason a Campaign action doesn't execute, this is the length of time Mautic waits before trying again.

* **Use date range for all views** - When viewing a Campaign, the date range of actions, conditions, decisions, and Contacts displayed in the tabs, Mautic uses this date range by default.

* **Use summary statistics** - Improves performance when viewing a Campaign with thousands of events per day by using summarized data. When you first turn on this setting you need to run a :ref:`cron job<campaign cron jobs>` to summarize existing data.

Email settings
**************

Email transport settings
========================

As Mautic uses the :xref:`Symfony Mailer` library since v5, it supports all Symfony Mailer core Plugins out of the box. 

SMTP transport
--------------

The SMTP transport is the default transport used for sending Emails with Mautic. It's configured in the Mautic configuration under the Email Settings tab. The configuration is the same as in the :xref:`Symfony Mailer` documentation.

Mautic now uses a specific way of providing the connection details for Email transports to interpret, known as a Data Source Name, or DSN. This is the example Data Source Name configuration mentioned in the :xref:`Symfony Mailer` documentation for SMTP:

.. code-block:: shell

    smtp://user:pass@smtp.example.com:port

Mautic creates this automatically from the values entered in the Email configuration:

.. image:: images/smtp-dsn.png
    :width: 400
    :alt: SMTP API DSN example

.. list-table:: Example DSN ``smtp://user:pass@smtp.example.com:port/path?option1=value1&option2=value2`` explained
    :widths: 10 20 150
    :header-rows: 1
    :stub-columns: 1

    * - DSN part
      - Example
      - Explanation
    * - Scheme
      - ``smtp``
      - Defines which transport Plugin handles the Email sending. It also defines which other DSN parts must be present.
    * - User
      - ``john``
      - Some transport wants username and password to authenticate the connection. Some public or private key. Some just API key.
    * - Password
      - ``pa$$word``
      - As mentioned previously, read the documentation for your particular transport and fill in the fields it requires. For SMTP enter the password in this field.
    * - Host
      - ``smtp.mydomain.com``
      - For SMTP, this is the domain name where your SMTP server is running. Other transports may have the domain handled within the Plugin, so they may instruct you to enter ``default`` here.
    * - Path
      - ``example/path``
      - This is usually empty. For SMTP this may be the path to the SMTP server. For other transports this may be the path to the API endpoint. Enter according to the documentation for your transport.
    * - Port
      - ``465``
      - Important for SMTP. The port value defines the encryption used. This is usually ``465`` for SSL or ``587`` for TLS. Avoid using port 25 for security reasons. For other transports this may be the port to the API endpoint.
    * - Options
      - ``timeout=10``
      - This is optional. This may be the timeout for the connection or similar configuration. The configuration allows you to create multiple options.

.. note::
  Use Mautic's global configuration to paste in the DSN information, especially the API keys and passwords. The values must be URL-encoded, and the configuration form does that for you. If you are pasting DSN settings directly into the ``config/local.php`` file, you must URL-encode the values yourself.


.. vale off

Example API transport installation
----------------------------------

.. vale on

.. warning::
  Installing Symfony Transports is possible when you've :doc:`installed Mautic via Composer </getting_started/how_to_install_mautic>`.

If you want to use :xref:`SendGrid` API instead of SMTP to send Emails, for example, you can install the official Symfony SendGrid Transport by running the following command mentioned alongside others in the :xref:`Symfony Mailer` documentation.

.. code-block:: shell

    composer require symfony/sendgrid-mailer

After that, you can configure the transport in the Mautic configuration. The example DSN is again mentioned in the :xref:`Symfony Mailer` documentation along with other transports. In the example of using the SendGrid API, the DSN looks like this:

.. code-block:: shell

    sendgrid+api://KEY@default

This is how you would configure Mautic's Email configuration:

  .. image:: images/sendgrid-api-dsn.png
    :width: 400
    :alt: SendGrid API DSN example

To replace the SendGrid API key, add it to the relevant field in the Email configuration and save. Mautic now uses the SendGrid API to send Emails.

.. warning::
  It's a nice perk that Mautic can use any transport provided by Symfony Mailer. However, be aware that such transports from Symfony **don't support batch sending, even via API**. They only send one Email per request, as opposed to a thousand Emails per request as is the case with some Mautic transports, which can make them slow at scale. They also **don't support transport callback handling used for bounce management**. If you plan to send larger volumes of Emails or need to use features which require callback handling, please consider using Email transports built specifically for such use. These Plugins are available in the :doc:`Mautic Marketplace </marketplace/marketplace>`.

The table below lists available transport Plugins created for Mautic to include support for batch sending and callback handling.

.. vale off

.. list-table:: 
   :widths: 40 60
   :header-rows: 1

   * - Link to Packagist
     - Command for installing
   * - :xref:`sparkpost-transport`
     - ``composer require ts-navghane/sparkpost-plugin``
.. vale on

Configuring the Queue
=====================

The system can either send Emails immediately or queue them for processing in batches by a :doc:`cron job </configuration/cron_jobs>`. Documentation relating to configuring the queue is in the :doc:`queue </queue/queue>` section.

Immediate delivery
------------------

This is the default means of delivery. As soon as an action in Mautic triggers an Email to send, it's sent immediately. If you expect to send a large number of Emails, you should use the queue. Sending Email immediately may slow the response time of Mautic if using a remote mail service, since Mautic has to establish a connection with that service before sending the mail. Also attempting to send large batches of Emails at once may hit your server's resource limits or Email sending limits if on a shared host.

Queued delivery
---------------

Mautic works most effectively with high send volumes if you use the queued delivery method. Mautic stores the Email in the configured spool directory until the execution of the command to process the queue. Set up a :doc:`cron job </configuration/cron_jobs>` at the desired interval to run the command:

.. code-block:: shell
    
    php /path/to/mautic/bin/console messenger:consume email

Some hosts may have limits on the number of Emails sent during a specified time frame and/or limit the execution time of a script. If that's the case for you, or if you just want to moderate batch processing, you can configure batch numbers and time limits in Mautic's Configuration. See the :doc:`cron job documentation </configuration/cron_jobs>` for more specifics.


Mail send settings
==================

.. image:: images/mail-send-settings.png
  :width: 600
  :alt: Screenshot showing Mail Send Settings Configuration in Mautic

* **Name to send mail as** - The default name Emails come from. This is typically something like ``{YourCompany Marketing Team}`` or ``{YourCompany}``.
  
* **Email address to send mail from** - The Email address for the name you're sending mail from. The address displays in the ``From:`` field when your Contacts receive your Emails.

.. note::

  Ensure that you configure your sender domain, ``DKIM``, bounce, and click tracking domains. For more information, see the :ref:`Email<emails>` documentation.

* **Reply to address** -  To have Contacts reply to a different address than the specified From address, add the desired address here. This is the default ``reply-to`` address where messages are sent from Mautic unless it is overridden in an individual Email. If this field is blank, Mautic uses the address specified in **Email address to send mail from**. The ``reply-to`` setting is useful if your configured sender domain - which you use in the from address - contains a subdomain that doesn't have MX records or is otherwise an address that can't receive Emails.
  
* **Custom return path (bounce) address** - Set a custom return path/bounce Email address for Emails sent from the system. Note that some mail transports, such as GMail, won't support this.

* **Mailer is owner** - If Contacts in Mautic have owners, select Yes to use the Contact owner as the sender of Emails to any Contacts they're listed as the owner for.

.. note:: 

    Mailer is owner overrides any other name or Email to send mail from, including the default and individual Emails. Every Contact owner's domain must have ``SPF`` and ``DKIM`` records. You can see this configuration for individual Emails, rather than globally.
    For more information see :doc:`Mailer is owner</channels/emails>`

* **Service to send mail through** - Select the Email service provider you use, and enter your credentials. 

See :ref:`here<contact's unsubscribe email preferences>` to set the Contact's Email subscription preferences.
  
Default frequency rule
======================

* **Do Not Contact more than <number> each <period>** - This limits the number of Marketing Messages a Contact receives in a certain period of time day, week, month. Transactional messages don't count towards this limit. You can adjust this at the individual Contact level, either manually or by Preference Center setting.

.. image:: images/default-frequency-rule.png
  :width: 600
  :alt: Screenshot showing Default Frequency Rule Configuration in Mautic

.. note:: 

  More information is available in the :doc:`Default Frequency Rule documentation</contacts/frequency_rules>`.

Monitored inbox settings
========================

.. image:: images/monitored-inbox-settings.png
  :width: 600
  :alt: Screenshot showing Monitored Settings Configuration in Mautic

* **Default Mailbox** - If your messages are going to bounce, this inbox is where you receive those bounce notifications.

* **Bounces** - A folder to monitor for new bounce messages or Emails.

* **Unsubscribe Requests** - A folder to monitor for new unsubscribe requests. 

* **Contact Replies** - Similar to the monitored inbox for bounces, this is the inbox Mautic checks for Contact replies. Using :ref:`Replies to Email<email settings>` decisions in any Campaign requires configuration. With ``Use custom connection settings?`` set to ``no``, Mautic checks the default mailbox. If set to ``yes``, you may track a different mailbox for replies.

Message settings
================

.. image:: images/message-settings.png
  :width: 600
  :alt: Screenshot showing Message Settings Configuration in Mautic

* **Text for the** ``{webview_text``} **token** - The message indicating the reader can view the Email in their browser. The default is; ``Having trouble reading this Email? Click here``.
  
  To change the text, change the message between the ``<a href="|URL|">`` and ``</a>`` tags. Don't change the ``|URL|`` text, because that's a token, which creates a unique URL for each Contact.

* **Default Email signature** - The signature for your default Emails, which pairs with the name & Email address in the **Mail Send** settings.

* **Append tracking pixel into Email body?** - To track Email opens, select **Yes**. Select **No** to prevent tracking, reporting on, and using decisions based on Email opens.

* **Convert embed images to Base64** - Select **Yes** to display embedded images in Emails using embedded base64 code rather than as embedded images.

* **Disable trackable URLs** - Removes tracking from URLs in your Emails. Select Yes to prevent tracking, reporting on, and using decisions based on link clicks. Some Email service providers don't like redirecting URLs. Using trackable URLs in your Emails may impact deliverability.
  
Unsubscribe settings
====================

.. image:: images/unsubscribe-settings.png
  :width: 600
  :alt: Screenshot showing Unsubscribe Settings Configuration in Mautic

* **Text for the {unsubscribe_text} token** -  Like the ``{webview_text}`` token,  this allows you to customize the **Unsubscribe** link. 

  For example - Edit between the ``<a href="|URL|">`` and ``</a>`` tags. Don't change the URL as it's tokenized. If you add ``{unsubscribe_url}`` as a token in the Email, you won't see this text.

* **Unsubscribed and resubscribed confirmation message** - If a Contact unsubscribes or resubscribes, this message displays on the page after the respective action. Don't edit the ``|EMAIL|`` or the ``|URL|`` token in the ``<a href>`` tag.

* **Show Contact preference settings** - Select **Yes** to direct the unsubscribe link to your configured Preference enter. If you haven't created a Preference Center, Mautic creates a default page based on the next 5 settings. The created page uses the default Theme for styling.

* **Show Contact Segment preferences** - Select **Yes** to allow a Contact to change which Segments they're part of on the Preference Center. Segments won't display on the Preference Center if they aren't active and public.

* **Show Contact frequency preferences** - Select **Yes** to allow an individual to limit the number of Marketing Messages they receive on each Channel from the Preference Center.

* **Show pause Contact preferences** - Select **Yes** to allow Contacts to turn-off messages from your Mautic account to their Email address for a specified date range. This action isn't a full unsubscribe action, and at the end of the date range, In this case, it sends the message again after the date range ends, as this isn't a full unsubscribe action.

* **Show Contact's Categories** - If you have Categories set for Contacts, Campaigns, Emails, etc., select Yes to allow the Contact to opt out of the Categories they choose from the Preference Center page.

* **Show Contact's preferred Channel option** - If you have multiple Channels available within your Mautic instance. For example; Email, ``SMS``, mobile push, web notifications, etc., Contacts can choose their preferred Channel. This can be useful if you are using the Marketing Messages feature of Mautic. More information about the Preference Center is available :doc:`here</contacts/preference_center>`.


.. vale off

How to track opened Emails
==========================

.. vale on

Mautic automatically tags each Email with a tracking pixel image. This allows Mautic to track when a Contact opens the Email and execute actions accordingly. Note that there are limitations to this technology - the Contact's Email client supporting HTML and auto-loading of images, and not blocking the loading of pixels. If the Email client doesn't load the image, there's no way for Mautic to know the opened status of the Email.

By default, Mautic adds the tracking pixel image at the end of the message, just before the ``</body>`` tag. If needed, one could use the ``{tracking_pixel}`` variable within the body content token to have it placed elsewhere. Beware that you shouldn't insert this directly after the opening ``<body>`` because this prevents correct display of pre-header text on some Email clients.

It's possible to turn off the tracking pixel entirely if you don't need to use it, in the Global Settings.

.. vale off

How to track links in Emails
============================

.. vale on

Mautic tracks clicks of each link in an Email, with the stats displayed at the bottom of each Email detail view under the Click Counts tab.


Form settings
*************

.. image:: images/form-settings.png
  :width: 600
  :alt: Screenshot showing Form Settings Configuration in Mautic

* **Do not accept submission from these domain names** - To block Contacts with specific Email domains from submitting your Forms, enter those domains in the dialog box. Select an option on each Form you want to apply this block to. You can restrict either specific Email aliases that belong to a domain or an entire domain. To block the entire domain, you can use wildcards (*).

Contact settings
****************

Contact merge settings
======================

.. image:: images/contact-merge-settings.png
  :width: 600
  :alt: Screenshot showing Contact Merge Settings Configuration in Mautic

* **Merge by unique fields with operator** - You can determine which operator to use when merging fields if there is more than one unique identifier.

Contact list settings
=====================

.. image:: images/contact-list-settings.png
  :width: 600
  :alt: Screenshot showing Contact List Settings Configuration in Mautic

* **Columns** - Select from the left which fields appear on the Contact lists (when you go to Contacts in the Mautic and view the list).

To display the fields, select them from the left and move them to the right column, or remove from the right column if you don't want them to appear in the list.

Import settings
===============

.. image:: images/import-settings.png
  :width: 600
  :alt: Screenshot showing Import Settings Configuration in Mautic

* **Automatically import in the background if the CSV has more rows than defined** - If there are more than the specified number of rows in an import file, the CSV automatically sets to import in the background which requires a :ref:`cron job<import contacts cron job>` to trigger. Set to 0 if you want to always import files in the background recommended for performance optimization.

Export settings
===============

.. image:: images/export-settings.png
  :width: 600
  :alt: Screenshot showing Export Settings Configuration in Mautic

* **Automatically export Contacts to CSV in the background** - If set to Yes, Mautic processes CSV exports of Contacts in the background and Mautic sends an Email with a link to download the file when it's processed.

Segment settings
****************

.. image:: images/segment-settings.png
  :width: 600
  :alt: Screenshot showing Segment Settings Configuration in Mautic

* **Show warning if Segment hasn't been rebuilt for X hours** - Every time a :ref:`cron jobs<segment cron jobs>` runs, Segments are rebuilt. If there is an error that prevents a Segment from rebuilding, Mautic displays a warning message. This field allows you to configure the allowable length of time between rebuilds, after which the warning message appears.

Company settings
****************

.. image:: images/company-merge-settings.png
  :width: 600
  :alt: Screenshot showing Company Merge Settings Configuration in Mautic

* **Merge by unique fields with operator** - You can determine which operator to use when merging fields if there is more than one unique identifier.

Queue settings
**************

Purpose of the queuing
======================

Mautic can optionally use a queuing mechanism for sending Emails. This feature is essential when running Mautic **at large scale**. It's planned to extend the tasks that can utilize queuing in the future.

When you enable queuing, Emails are no longer sent immediately - for example, within the browser - but instead, Mautic places them in a queue and sends them later using queue consumers - also known as workers. Using consumers helps to offload the workload of your server, and allows easier scaling of your Mautic instance.

Mautic doesn't use queues by default
====================================

A fresh instance of Mautic has **the queuing feature turned off** (the queue DSN configuration is ``"sync://"``) as shown in the following screenshot.

.. image:: images/queue-disabled.png
  :width: 600
  :alt: Queue turned off

How to enable the queuing
=========================

First you need to decide on a queuing transport to drive your queue. There are several options available at the moment. It's up to you to choose which one fits your needs the best.

**Currently available transports:**

* :ref:`Doctrine`
* :ref:`Redis`
* :ref:`AMQP`
* :ref:`Beanstalkd`
* :ref:`Amazon SQS`

Doctrine
--------
This transport is easy to setup as it doesn't require installing any additional extension.

It uses database table ``messenger_messages`` for storing messages - you can change the table name via options. The screenshot below shows the basic settings.

.. image:: images/queue-doctrine.png
  :width: 600
  :alt: Example of Doctrine transport

See :xref:`queue-doctrine-transport` for the complete list of configuration options.

Redis
-----
This transport requires the Redis PHP extension (>=4.3) and a running :xref:`Redis` server (^5.0). Once met, the typical configuration looks as follows.

.. image:: images/queue-redis.png
  :width: 600
  :alt: Example of Redis transport

See :xref:`queue-redis-transport` for the complete list of configuration options.

AMQP
----
The AMQP transport requires the AMQP PHP extension and a running AMQP service like :xref:`RabbitMQ`. See the screenshot below for an example of the configuration.

.. image:: images/queue-amqp.png
  :width: 600
  :alt: Example of AMQP transport

See :xref:`queue-amqp-transport` for the complete list of configuration options.

Beanstalkd
----------
The Beanstalkd transport requires a running :xref:`Beanstalkd` service and a Composer dependency installed via ``composer require symfony/beanstalkd-messenger``.
After installing the Composer dependency, you can fill in the configuration as follows.

.. image:: images/queue-beanstalkd.png
  :width: 600
  :alt: Example of Beanstalkd transport


.. vale off

See :xref:`queue-beanstalkd-transport` for the complete list of configuration options.

.. vale on

Amazon SQS
----------
The Amazon SQS transport is ideal when hosting your Mautic instance on AWS. You need to install a Composer dependency via ``composer require symfony/amazon-sqs-messenger``. See the example of the configuration below.

.. image:: images/queue-amazon-sqs.png
  :width: 600
  :alt: Example of Amazon SQS transport

See :xref:`queue-amazon-sqs` for the complete list of configuration options.

How to consume messages from the Queue
======================================

To start consuming the messages from the Queue, you need to run the following Symfony command.

.. code-block::

    php bin/console messenger:consume email

If you don't use Kubernetes in your environment, use a process manager like ``Supervisor`` or ``systemd`` to keep your worker/s running. More on this at :xref:`queue-consuming-messages`

Advanced setting
================

Retry strategy
--------------

When the processing of a message fails, Mautic sends the message back to the queue for another try. You can adjust this behaviour in this section.
See :xref:`queue-retries-failures` for more details.

The screenshot below shows the default values.

.. image:: images/queue-retry-strategy.png
  :width: 600
  :alt: Retry strategy defaults

Queue for failures
------------------

If a message fails all its retries, it's discarded by default. To avoid this happening, you can optionally configure a Queue for failures.

For more details see the documentation on :xref:`queue-saving-retrying-failed-messages`.

The screenshot below shows the example of configuring the failure queue using the Doctrine transport.

.. image:: images/queue-failures.png
  :width: 600
  :alt: Example of failure configuration

Notification settings
*********************

.. image:: images/campaign-notification-settings.png
  :width: 600
  :alt: Screenshot showing Campaign Notification Settings Configuration in Mautic

.. image:: images/webhook-notification-settings.png
  :width: 600
  :alt: Screenshot showing Webhook Notification Settings Configuration in Mautic

If a Campaign or Webhook is automatically deactivated because of a high volume of errors, Mautic sends a notification alerting Users.

* **Send notification to author** - Set this field to Yes to send an Email notification to the User who created the deactivated Campaign or Webhook. Deleted Users don't receive notifications.

.. vale off

Landing Page settings
*********************

.. vale on

.. image:: images/landing-page-settings.png
  :width: 600
  :alt: Screenshot showing Landing Page Settings Configuration in Mautic

* **Show Category in Page URL?** - If you use Categories, the Landing Page's associated Category displays in the URL if you select Yes.

* **Analytics script** - To track Landing Page visits and activity in other platforms such as Google Analytics, add those tracking scripts here.

Tracking settings
*****************

Mautic tracking settings
========================

.. image:: images/tracking-settings.png
  :width: 600
  :alt: Screenshot showing Tracking Settings Configuration in Mautic

* **Tracking code** - Insert this code on any page you would like to have tracked in Mautic before the ending ``</body>`` tag.

.. note:: 

    The default tracking code provided in a new instance updates and changes after you set up a new custom domain or when you make changes to an existing one. You must use the new tracking code that reflects the new or edited custom domain. If you are using the Plugin for WordPress, Drupal, or Joomla, re-enter your account information in the Plugin.

* **Identify visitor by tracking URL** - Select **Yes** to have Mautic begin tracking a Contact after the Contact clicks a link in an Email on a device where no cookie exists.

* **Anonymize IP** - Select **Yes** to not store full IP addresses for your visitors/Contacts. This setting aids customers in achieving General Data Protection Regulation compliance.

* **Identify visitors by IP** - Select **Yes** to use the IP address to identify Contacts. It's possible to track unidentified visitors with the same IP address as an existing Contact. This may result in undesirable outcomes with large Companies who use the same externally facing IP address.

* **Do Not Track 404 error for anonymous Contacts** - Select **Yes** to not track page hits on any 404 error page tracked by the tracking code. This option helps prevent filling your logs with hits from bots.
  
.. note:: 

  * The tracking code automatically detects the Preferred Timezone and Preferred Locale fields.
  * Landing Pages including 4-byte UTF-8 characters, such as emojis and some Chinese or other non-Latin characters, in the Landing Page title or URL aren't tracked on a Contact's activity history in Mautic. Mautic tracks all Latin characters used in English and other western languages which are of 1-byte.

Facebook pixel
==============

.. image:: images/facebook-pixel-settings.png
  :width: 600
  :alt: Screenshot showing Facebook Pixel Settings Configuration in Mautic

* **Facebook Pixel ID** - Enter your Facebook Pixel ID and select the options you'd like to use the pixel for.

* **Enabled on your tracking Landing Page** - Select Yes to have Mautic append the Facebook Pixel to the Mautic tracking code to track Landing Pages where the tracking code exists.

* **Enabled on Mautic Landing Page** - Select Yes to have Mautic add the Facebook Pixel to Mautic Landing Pages.


Google analytics
================

.. image:: images/google-analytics-settings.png
  :width: 600
  :alt: Screenshot showing Google Analytics Settings Configuration in Mautic

* **Google Analytics ID** - Enter your Google Analytics ID and select the options you'd like to use the pixel for.

* **Enabled on your tracking Landing Page** - Select Yes to have Mautic append the Google Analytics script to the Mautic tracking code to track Landing Pages where the tracking code exists.

* **Enabled on Mautic Landing Page** - Select Yes to have Mautic add the Google Analytics script to Mautic Landing Pages.

* **Enabled IP** ``Anonymization`` - For subscribers sensitive to General Data Protection Regulation or other data privacy laws and regulations, select Yes to anonymize the IP address of web visitors before sending it to Google Analytics.* 

Report settings
***************

.. image:: images/report-settings.png
  :width: 600
  :alt: Screenshot showing Report Settings Configuration in Mautic

* **Always quote data in CSV export** - Select Yes to wrap each Mautic field in double quotation marks when exported to a CSV file. For example: ``"First Name",”Last Name”,””, "some text"``.

Text message settings
*********************

.. image:: images/text-message-settings.png
  :width: 600
  :alt: Screenshot showing Text Message Settings Configuration in Mautic

* **Select default transport to use** - If you have configured a delivery service for SMS messages, select the service here to send messages. You must configure a delivery service before selecting it here.

User/Authentication settings
****************************

SAML/SSO settings
=================

.. image:: images/SMAL-settings.png
  :width: 600
  :alt: Screenshot showing SAML/SSO Settings Configuration in Mautic

* **Identity provider metadata file** - Upload the metadata XML file from your Identity Provider (IDP) here.

* **Default Role for created Users** - You can select one of those Roles as the default for Users created using Single Sign-On by creating :doc:`User Roles</users_roles/managing_roles>` in the Roles section of the settings panel. If empty, Single Sign-On won't create any Mautic Users. See :doc:`Users and Roles</users_roles/managing_roles>`.

Enter the names of the attributes the configured IDP uses for the Mautic User fields. Match the field name from your identity provider to the field name Mautic uses for User creation.

* **Email**
* **First name**
* **Last name**
* **Username**

Use a custom X.509 certificate and private key to secure communication between Mautic and the IDP. 

Upload your:

* **X.509 certificate**
* **Private key file**

Enter your **Private key encryption password**

Webhook settings
****************

.. image:: images/webhook-settings.png
  :width: 600
  :alt: Screenshot showing Webhook Settings Configuration in Mautic

* **Queue Mode** -  Select how to process Webhook events. The process immediately executes the Webhook event as soon as it arrives. The queue mode improves performance by only adding the event to the queue and requires processing by a :ref:`cron command<webhooks cron job>`.

* **Order of the queued events** - Process the events in chronological or reverse chronological order if a Webhook has a queue of multiple events.
  
Social settings
***************

.. image:: images/social-settings.png
  :width: 600
  :alt: Screenshot showing Social Settings Configuration in Mautic

* **Twitter Handle Field** - This field stores the Twitter username for Users added to Mautic through Social Monitoring.
