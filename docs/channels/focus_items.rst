Focus Items
###########

Focus Items allow you to engage Users on your site through bars, modals, notifications, popups, and light boxes. It's possible to initiate Focus Items at different times and with different actions such as exit intent.

You can find Focus Items listed under the Channels menu.

Focus Item settings
*******************
There are several different types of Focus Items, and many ways to configure them to deliver your strategic marketing goals.

Types of Focus Item
===================

There are three different types of Focus Item that you can create within Mautic. These allow you to achieve different marketing goals with your Focus Items. Select the appropriate option for your needs.

  .. image:: images/focus_items/focus_item_types.png
    :width: 400
    :alt: Screenshot showing the types of Focus Items.

- **Collect Data** - This option presents a Form - which must already exist - within the Focus Item. This allows you to gather more information about your website visitors. Mautic considers a successful conversion on this type of Focus Item when there is a submission of this Form. This option is great for capturing simple information - for example a newsletter registration Form.
- **Display a Notice** - This option presents a message to your visitors. There is no option for detecting a conversion with this type of Focus Item. This option is great for announcements and important messages.
- **Emphasize a link** - This option allows you to drive visitors to a specific link which might be a resource on your website, a Mautic Landing Page, or any other web-based resource. Mautic considers a link click to be a successful conversion with this Focus Item. This option is great for Landing Pages to highlight a promotion or a sale - it displays a button to click which directs the visitor to a given link.

Engagement options
==================

For each type of Focus Item, there are settings to configure which control the triggering of the Focus Item, and how they interact with the visitor.

  .. image:: images/focus_items/focus_item_engagement.png
    :width: 400
    :alt: Screenshot showing the engagement settings for Focus Items.

- **Animate** - When set to Yes, this applies a slide-in animation to the Focus Item. When set to No, the item appears without any kind of sliding motion.
- **When to engage** - This setting controls the Focus Item shows. There are several options:
   - **Upon arrival** - As soon as a visitor lands on the page
   - **After slightly scrolling down** - Wait a little while until the visitor starts to scroll down the page
   - **After scrolling to the middle** - Wait until the visitor scrolls to the middle of the page
   - **After scrolling to the bottom** - Wait until the visitor scrolls right to the bottom of the page
   - **Visitor intends to leave** - If the visitor's cursor moves over the address bar, or from the page to the tabs - for example to close the tab or open a new tab
- **Timeout before engage** - This option allows you to set the delay in seconds after reaching the option selected in **When to engage**. For example, if the setting is **Upon arrival** and **Timeout before engage** is 2 seconds, the Focus Item appears two seconds *after* the visitor lands on the page.
- **How often to engage** - This option allows you to control how frequently the Focus Item displays to visitors. The options available include:
   - **Every page** - Show on every page the visitors engages with on your website
   - **Once per session** - Show once for each time that the visitor accesses your website
   - **Every 2 minutes** - Show the Focus Item every two minutes that the visitor is on your website
   - **Every 15 minutes** - Show the Focus Item every 15 minutes that the visitor is on your website
   - **Once per hour** -  Show the Focus Item once every hour that the visitor is on your website
   - **Once per day** - Show the Focus Item once per day that the visitor is on your website
- **Stop engaging after a conversion** - This option is only available for the types which track a conversion (Collect Data and Emphasize a Link).  If set to Yes, the Focus Item no longer displays if the visitor has either submitted the Form (Collect Data type) or clicked on the link (Emphasize a Link type).
- **Stop engaging after closing Focus** - This option is available for Focus Items and uses cookies. If set to Yes, the Focus Item no longer displays to the visitor after they have interacted with it, until they clear their cookies.

Styles
======

There are four styles to choose from when creating a Focus Item. Each style has different configuration options relevant to the layout they provide.

  .. image:: images/focus_items/focus_item_styles.png
    :width: 400
    :alt: Screenshot showing the styles for Focus Items.

Bar
~~~
The Bar style creates a line across the top or bottom of the page, which includes the content of your Focus Item.

- **Allow hide** - when set to Yes, website visitors have a small arrow to hide the bar. The arrow shows on the right hand side of the bar. Once clicked, the bar shrinks to hide the content but the arrow is still be visible in case they want to maximise it again with a single click. If set to No, the visitor can't hide the bar.
- **Push page down** - This option allows the bar to push the page content up or down under the bar if set to Yes. If set to No, the bar covers the content at the top or bottom of the page depending on placement setting.
- **Make sticky** - If set to Yes, the bar stays anchored in position even when the visitor scrolls the page. If set to No, the bar won't anchored and disappears as the visitor scrolls the page, and re-appears as they reverse the scroll.
- **Placement** - This option allows you to display the bar at the top or the bottom of the page.
- **Size** - This option allows you to specify the thickness of the bar, and the font size. The options include:
    - **Large** - 50px height and 17pt font
    - **Regular** - 30px height and 14pt font

Modal
~~~~~
The Modal style is probably the most popular style, and is often referred to as a pop-up or a light box.

Modals are small boxes which appear aligned horizontally centred on the page. The content behind the pop-up darkens when the Focus Item is active, which helps to draw attention - focus - to the pop-up.

- **Placement** - This option allows you to select whether you would like the Modal to appear at the top, middle or bottom of the page.

Notification
~~~~~~~~~~~~

The Notification style is a small box which appears, sometimes referred to as a pop-up. Unlike with the Modal style, the pop-up shows in one of the four corners of the page, and the main content underneath the notification isn't darkened out behind the pop-up.

Visitors can choose to close this type of Focus Item with the *X* button in the top right corner of the notification.

- **Placement** - This option allows you to select the corner to display the notification.

Full page
~~~~~~~~~

The full page Focus Item completely takes over the whole page, hiding the page content until the visitor clicks the *X* button in the top right hand corner of the Focus Item.

There are no additional configuration options for this style of Focus Item.

Colors
======

By default, Mautic determines the top colors extracted from the snapshot. Four colors are currently supported. You can customize colors by using the color picker or entering a hex code.

- **Primary color**
  - For the Bar style, the primary color is the background color of the bar
  - For the Modal, Notification and full page styles, the primary color is the outline around the Focus Item with a thicker line on top than on the other three sides.
- **Text color** - The color of the headline text entered in the Content section of the Focus Item editor
- **Button color** - The background color for the button on the Collect Data and Emphasize Link Focus Item types. This option isn't available for the Display a notice Focus Item type.
- **Button text color** - The color for the button text on the Collect Data and Emphasize Link Focus Item types. This option isn't available for the Display Notice Focus Item type.

Content
=======
There are three editing modes to choose from when customizing Focus Items.

  .. image:: images/focus_items/focus_item_content.png
    :width: 400
    :alt: Screenshot showing the content options for creating Focus Items.

Basic
~~~~~
This editor mode allows a simplified experience with a few fields - depending on the Focus Item type - with the content being automatically rendered on the Focus Item as it's created.

- **Headline** - This is the main text used on the Focus Item. The aim is to capture the visitor's interest and attention.
- **Tagline** - This option is only available for Emphasize a Link Focus Item types. It allows you to provide a second line of text to add more incentive for the visitor to click the link. This field is optional.
- **Font** - This option allows you to select from available fonts used in the Focus Item. The font list isn't customizable.
- **Select the Form to insert** - This option is only available for Collect Data Focus Item types. It allows you to select an existing Mautic Form to use with the Focus Item. For styling and formatting reasons, you may want to create a Form specifically for the Focus Item, adding styling attributes to the Attributes tab on the Form fields.
- **Link text** - This option is only available for Emphasize a Link Focus Item types. It allows you to specify the text used on the Focus Item's button.
- **Link URL** - This option is only available for Emphasize a Link Focus Item types. It allows you to specify the URL where you'd like to drive visitors with the Focus Item.
- **Open in a new window** - This option is only available for Emphasize a Link Focus Item types. If set to Yes, this ensures that the link opens in a new window. If set to No, the link opens in the current tab.

Editor
~~~~~~
This allows the User to edit the content with the global editor available in Mautic.

HTML
~~~~
This allows the User to enter HTML into a blank field for a fully customized Focus Item.

.. note:: 
    If you decide to switch editing styles, ensure that you clear the data from the previous style, otherwise Mautic may not display the final intended content.


Creating a Focus Item
*********************

To create a new Focus Item, go to Channels > Focus Items and click the New button.

.. warning:: 
    Some websites won't allow the preview to display. For the preview to work, the site must use an SSL certificate, and it must not block iframe previews with the ``x-frame-options: SAMEORIGIN`` header. An error will be displayed in the Focus Item builder if these conditions are not met.

When creating a new Focus Item, you can set the following fields:

**Name** - A name used internally to identify the Focus Item

**Website** - A website you would like to use to preview the Focus Item as you are building it - see preceding note, some websites won't allow this feature. If this is a problem, leave the URL field blank.

**Category** - Assign a Category to help you organize your Focus Items.

**Active** - Whether the Focus Item is available for use - active - or not available - inactive.

.. vale off

**Activate at (date/time)** - This allows you to define the date and time at which this Text Message is available for sending to Contacts

**Deactivate at (date/time)** - This allows you to define the date and time at which this Text Message ceases to be available for sending to Contacts.

.. vale on

**Google Analytics UTM tags** - Mautic supports UTM tagging in Emails, Focus Items, and Landing Pages. Any UTM tags with values populated are automatically appended to the end of any links used in the Focus Item. See :doc:`/channels/utm_tags` for more information.

  .. image:: images/focus_items/focus_item_create.png
    :width: 400
    :alt: Screenshot showing the creation of a Focus Item.

.. vale off

Using the Focus Item builder
============================

.. vale on

After you specify the general information for the Focus Item, click the builder option in the top right corner. If you've specified a URL in the Website field on the details page, the system displays a preview. If you don't see a preview, the website might block iframe previews. Hence, you may need to add the Focus Item to a development or staging environment without these security restrictions - if available - to see the preview.

.. note:: 
    The preview of the website doesn't appear until you select a style from the options on the Focus Item Builder.

  .. image:: images/focus_items/focus_item_builder.png
    :width: 400
    :alt: Screenshot showing the Focus Item Builder

You can use the menu on the sidebar to configure the Focus Item to your liking. The preview area on the left allows you to see how it appears on your website. You can also use the mobile phone icon at the top right to switch to a responsive view. This is important to ensure that you aren't blocking key elements of the User Experience on mobile devices.

  .. image:: images/focus_items/focus_item_builder_responsive.png
    :width: 400
    :alt: Screenshot showing the Focus Item Builder in responsive mode.

Using Focus Items
*****************

Once you have created your Focus Item, you're ready to activate it to your website. If you're not quite ready for the Focus Item to go live but you need to get it set up on your website, set the Focus Item to inactive.

Deploying to a website
======================

When you save the Focus Item, Mautic shows the code snippet required to display it on your website in a green box on the Focus Item overview.

  .. image:: images/focus_items/focus_item_embed.png
    :width: 400
    :alt: Screenshot showing the Focus Item code to embed within a website.

.. note:: 
    You may need assistance from your web development team to implement the Focus Item tracking code on your website.  

    You must also ensure that you have specified your website's domain where you expect to use the Focus Item in the CORS settings for your Mautic instance, otherwise it won't appear. To verify this, go to Settings > Configuration > System Settings > CORS Settings and set Restricted Domains to Yes. Ensure that you specify your domain in the relevant field. Alternatively (but not recommended, as this would allow other websites to display your Focus Items), set Restrict Domains to No and don't specify your domains.

.. vale off

Deploying through a Campaign
============================

.. vale on

It's possible to trigger a Focus Item to appear as part of a Campaign workflow. This doesn't require you to paste the Focus Item code onto your website as it's delivered through the existing Mautic Tracking Code.

Within the Campaign, add a decision for ``Visits a Page``, and then select the Action of ``Show Focus Item``. Note that you must precede it by ``Visits a Page`` to trigger the Focus Item.

.. warning:: 
    Sometimes the Campaign Action can be unreliable and it's dependent on your Campaign steps, so it's recommended to use the direct embedding method in most cases.

Measuring success
*****************

When using the Emphasize a Link type, Mautic displays the link on the Focus Item overview where you can view the number of unique clicks.

If you change the link in a Focus Item after deployment, Mautic lists all links in the overview.

Additionally, Mautic applies UTM tags on Focus Items to both Form submissions and link clicks. If you are using a Focus Item to submit a Form, it's recommended that you have a Submit Action on the Form to record the UTM tags.