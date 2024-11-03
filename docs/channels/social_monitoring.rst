.. vale off

Social Monitoring
#################

.. vale on

It's possible to add Contacts to Mautic through monitoring Twitter for mentions and hashtags.

Requirements
************

- You must first configure the :doc:`/plugins/twitter` Plugin
- You must trigger the Social Monitoring :doc:`cron job </configuration/cron_jobs>` periodically.

.. vale off

Creating a Social Monitor
*************************

.. vale on

To create a new Social Monitor, go to Channels > Social Monitoring and click New.

Mautic offers two options when creating a Social Monitor:

- **Twitter mention** - Any time someone mentions a specified username, Mautic creates them as a Contact
- **Twitter hashtag** - Any time someone uses a specified hashtag in a tweet, Mautic creates them as a Contact.

  .. image:: images/social_monitoring/social_monitor.jpeg
    :width: 400
    :alt: Screenshot showing the creation of a new Social Monitor.

Social mentions
===============

When selecting the Twitter Mention monitoring method, the following fields are available:

- **Twitter mention** - The Twitter handle you want to track mentions of. Don't include the @ symbol - for example ``mauticcommunity``.
- **Description** - A description to use internally within Mautic to tell the marketer what the monitor is tracking.
- **Match Contact names** - If set to Yes, Mautic tries to match the names of Contacts created from Twitter and associate the Twitter account with their existing Contact record. If set to No, this won't happen and you are likely to experience duplicated Contacts.

There are also the standard Mautic fields available:

**Active** - This allows you to set the activation status of the Social Monitor. Deactivated Social Monitors won't collect new Contacts.

.. vale off

**Activate at (date/time)** - This allows you to define the date and time at which this Social Monitor is monitoring for new Contacts. You might use this to coincide with an event, for example.

**Deactivate at (date/time)** - This allows you to define the date and time at which this Social Monitor is monitoring for new Contacts.

.. vale on

**Contact Segment** - This allows you to define the Segment/s in Mautic that the Contacts join if detected with this Social Monitor. This can be useful for identifying people who are talking about your brand, and directly add them to a Segment to take further action.

  .. image:: images/social_monitoring/social_monitoring_mentions.png
    :width: 400
    :alt: Screenshot showing the creation of a new Twitter Mentions Social Monitor.

Hashtags
========

When selecting the Twitter Hashtags monitoring method, the following fields are available:

- **Twitter hashtag** - The Twitter hashtag mentions you want to track. Don't include the # symbol - for example ``mautic``.
- **Description** - A description to use internally within Mautic to tell the marketer what the monitor is tracking.
- **Match Contact names** - If set to Yes, Mautic tries to match the names of Contacts created from Twitter and associate the Twitter account with their existing Contact record. If set to No, this won't happen and you are likely to experience duplicated Contacts.

There are also the standard Mautic fields available:

**Active** - This allows you to set the activation status of the Social Monitor. Deactivated Social Monitors won't collect new Contacts.

.. vale off

**Activate at (date/time)** - This allows you to define the date and time at which this Social Monitor is monitoring for new Contacts. This might be used to coincide with an event, for example.

**Deactivate at (date/time)** - This allows you to define the date and time at which this Social Monitor ceases to monitor for new Contacts.

.. vale on

**Contact Segment** - This allows you to define the Segment/s in Mautic that the Contacts join if detected with this Social Monitor. This can be useful for identifying people who are talking about your brand, and directly add them to a Segment to take further action.

  .. image:: images/social_monitoring/social_monitoring_hashtags.png
    :width: 400
    :alt: Screenshot showing the creation of a new Twitter Hashtags Social Monitor.