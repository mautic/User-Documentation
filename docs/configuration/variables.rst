Variables
#########

.. tip:: 
  Default Value

  The default value - sometimes called Fallback Text - is specified after the ``|`` character. Consider this Email salutation:

  ``Hi {contactfield=firstname|there},``

Contact fields
**************

See :doc:`managing custom fields </contacts/custom_fields>` for more information.

.. list-table:: 
   :widths: 100 100
   :header-rows: 1

   * - Variable name
     - Variable syntax
   * - Attribution
     - ``{contactfield=attribution}``
   * - Attribution Date
     - ``{contactfield=attribution_date}``
   * - Address Line 1
     - ``{contactfield=address1}``
   * - Address Line 2
     - ``{contactfield=address2}``
   * - Country
     - ``{contactfield=country}``
   * - City
     - ``{contactfield=city}``
   * - Company
     - ``{contactfield=company}``
   * - Contact ID
     - ``{contactfield=id}``
   * - Email
     - ``{contactfield=email}``
   * - Facebook
     - ``{contactfield=facebook}``
   * - Fax
     - ``{contactfield=fax}``
   * - First Name
     - ``{contactfield=firstname}``
   * - Foursquare
     - ``{contactfield=foursquare}``
   * - Google+
     - ``{contactfield=googleplus}``
   * - Instagram
     - ``{contactfield=instagram}``
   * - IP Address
     - ``{contactfield=ipAddress}``
   * - Last Name
     - ``{contactfield=lastname}``
   * - LinkedIn
     - ``{contactfield=linkedin}``
   * - Mobile Number
     - ``{contactfield=mobile}``
   * - Phone Number
     - ``{contactfield=phone}``
   * - Position
     - ``{contactfield=position}``
   * - Skype
     - ``{contactfield=skype}``
   * - State
     - ``{contactfield=state}``
   * - Twitter
     - ``{contactfield=twitter}``
   * - Title
     - ``{contactfield=title}``
   * - Website
     - ``{contactfield=website}``
   * - Zip Code
     - ``{contactfield=zipcode}``
  
Contact Owner fields
*********************
  
.. list-table:: 
   :widths: 100 100
   :header-rows: 1
  

   * - Variable name
     - Variable syntax
   * - First Name
     - ``{ownerfield=firstname}``
   * - Last Name
     - ``{ownerfield=lastname}``
   * - Email
     - ``{ownerfield=email}``
   * - Position
     - ``{ownerfield=position}``
   * - Signature
     - ``{ownerfield=signature}``

Company Contact fields
***********************

See :doc:`Companies</companies/companies_overview>` for more information.

.. list-table:: 
   :widths: 100 100
   :header-rows: 1

   * - Variable name
     - Variable syntax
   * - Address Line 1 (Company)
     - ``{contactfield=companyaddress1}``
   * - Address Line 2 (Company)
     - ``{contactfield=companyaddress2}``
   * - Annual Revenue (Company)
     - ``{contactfield=companyannual_revenue}``
   * - City (Company)
     - ``{contactfield=companycity}``
   * - Country (Company)
     - ``{contactfield=companycountry}``
   * - Description (Company)
     - ``{contactfield=companydescription}``
   * - Email (Company)
     - ``{contactfield=companyemail}``
   * - Fax (Company)
     - ``{contactfield=companyfax}``
   * - Industry (Company)
     - ``{contactfield=companyindustry}``
   * - Name
     - ``{contactfield=companyname}``
   * - Number of Employees (Company)
     - ``{contactfield=companynumber_of_employees}``
   * - Phone Number (Company)
     - ``{contactfield=companyphone}``
   * - State (Company)	
     - ``{contactfield=companystate}``
   * - Website (Company)
     - ``{contactfield=companywebsite}``
   * - Zip Code (Company)
     - ``{contactfield=companyzipcode}``

.. tip:: 
  Custom Company Fields

  The syntax for custom Company fields is different than the core Company field syntax. You must **not** add the word "Company" in the variable, but instead treat it like a "contactfield":

Mautic Component tokens
***********************

See :doc:`Components</components/assets>` and :doc:`Manage Pages</components/landing_pages>` for more information.

.. list-table:: 
   :widths: 100 100
   :header-rows: 1
  

   * - Variable name
     - Variable syntax
   * - Asset link for Asset id#
     - ``{assetlink=25}``
   * - Focus Item id#
     - ``{focus=4}``
   * - Form id#
     - ``{form=83}``
   * - Landing Page link for page id#
     - ``{pagelink=17}``

Email specific tokens
*********************

See :doc:`Manage Emails</channels/emails>` for more information.

.. list-table:: 
   :widths: 100 100
   :header-rows: 1
  

   * - Variable name
     - Variable syntax
   * - Signature
     - ``{signature}``
   * - Subject
     - ``{subject}``
   * - Tracking pixel
     - ``{tracking_pixel}``
   * - Unsubscribe Text
     - ``{unsubscribe_text}``
   * - Web View Text
     - ``{webview_text}``
   * - Web View URL
     - ``{webview_url}``

Landing Page tokens
*********************

See :doc:`/components/landing_pages` for more information.

.. list-table:: 
   :widths: 100 100
   :header-rows: 1
  

   * - Variable name
     - Variable syntax
   * - Meta Description
     - ``{pagemetadescription}``
   * - Title
     - ``{pagetitle}``
   * - Language bar
     - ``{langbar}``
   * - Share Buttons
     - ``{sharebuttons}``
   * - Success Message
     - ``{successmessage}``

Preference Center Landing Page tokens
*************************************

See :doc:`customizing preference center</contacts/preference_center>` for more information.

.. list-table:: 
   :widths: 100 100
   :header-rows: 1
  

   * - Variable name
     - Variable syntax
   * - Lead Identifier
     - ``{leadidentifier}``
   * - Category List
     - ``{categorylist}``
   * - Segment List
     - ``{segmentlist}``
   * - Preferred Channel
     - ``{preferredchannel}``
   * - Channel Frequency
     - ``{channelfrequency}``
   * - Save Preferences
     - ``{saveprefsbutton}``

Dynamic Web Content tokens
**************************

.. list-table:: 
   :widths: 100 100
   :header-rows: 1
  

   * - Variable name
     - Variable syntax
   * - [Dynamic Content 1] | for example User-defined variable name
     - ``{dynamiccontent="Dynamic Content 1"}``

Contact Monitoring
******************

See :ref:`Contact Monitoring<Contact tracking>` for more information.

.. list-table:: 
   :widths: 100 100
   :header-rows: 1
  

   * - Variable name
     - Variable syntax
   * - Language
     - ``{language}``
   * - Title
     - ``{title}``
   * - Landing Page Title
     - ``{page_title}``
   * - URL
     - ``{url}``   
   * - Landing Page URL
     - ``{page_url}``
   * - Referrer
     - ``{referrer}``
   * - Tracking pixel
     - ``{tracking_pixel}``
   * - UTM Campaign
     - ``{utm_campaign}``
   * - UTM Content
     - ``{utm_content}``
   * - UTM Medium
     - ``{utm_medium}``
   * - UTM Source
     - ``{utm_source}``
   * - UTM Term
     - ``{utm_term}``

Search filters
**************

See the :ref:`Search<search>` page for more information.

Alphabetical list
*****************

.. list-table:: 
   :widths: 40 50
   :header-rows: 1

   * - Variable name
     - Variable syntax
   * - Address Line 1
     - ``{contactfield=address1}``
   * - Address Line 1 (Company)
     - ``{contactfield=address1}``
   * - Address Line 2
     - ``{contactfield=address2}``
   * - Address Line 2 (Company)
     - ``{contactfield=companyaddress2}``
   * - Annual Revenue (Company)
     - ``{contactfield=companyannual_revenue}``
   * - Asset link for Asset id#
     - ``{assetlink=25}``
   * - Attribution
     - ``{contactfield=attribution}``
   * - Attribution Date
     - ``{contactfield=attribution_date}``
   * - Category List (Preference Center)
     - ``{categorylist}``
   * - Channel Frequency (Preference Center)
     - ``{channelfrequency}``
   * - City
     - ``{contactfield=city}``
   * - City (Company)
     - ``{contactfield=companycity}``
   * - Country
     - ``{contactfield=country}``
   * - Country (Company)
     - ``{contactfield=companycountry}``
   * - Company
     - ``{contactfield=company}``
   * - Contact ID
     - ``{contactfield=id}``
   * - Description (Company)
     - ``{contactfield=companydescription}``
   * - [Dynamic Content 1]for example: user-defined variable name
     - ``{dynamiccontent="Dynamic Content 1"}``
   * - Email
     - ``{contactfield=email}``
   * - Email (Company)
     - ``{contactfield=companyemail}`` 
   * - Facebook
     - ``{contactfield=facebook}``
   * - Fax
     - ``{contactfield=fax}``
   * - Focus Item id#
     - ``{focus=4}``
   * - Form id#
     - ``{form=83}`` 
   * - Fax (Company)
     - ``{contactfield=companyfax}`` 
   * - First Name
     - ``{contactfield=firstname}``
   * - Foursquare
     - ``{contactfield=foursquare}``
   * - Google+
     - ``{contactfield=googleplus}``
   * - Instagram
     - ``{contactfield=instagram}``
   * - IP Address
     - ``{contactfield=ipAddress}``
   * - Landing Page link for page id#
     - ``{pagelink=17}``
   * - Language bar
     - ``{langbar}`` 
   * - Last Name
     - ``{contactfield=lastname}``
   * - Contact Identifier (Preference Center)
     - ``{leadidentifier}``  
   * - LinkedIn
     - ``{contactfield=linkedin}``
   * - Meta Description (Landing Page)
     - ``{pagemetadescription}``  
   * - Mobile Number
     - ``{contactfield=mobile}``
   * - Name (Company)	
     - ``{contactfield=companyname}``
   * - Number of Employees (Company)	
     - ``{contactfield=companynumber_of_employees}`` 
   * - Phone Number
     - ``{contactfield=phone}`` 
   * - Phone Number (Company)
     - ``{contactfield=companyphone}`` 
   * - Position
     - ``{contactfield=position}``
   * - Save Preferences (Preference Center)	
     - ``{saveprefsbutton}`` 
   * - Segment List (Preference Center)
     - ``{segmentlist}`` 
   * - Signature
     - ``{signature}`` 
   * - Skype
     - ``{contactfield=skype}``
   * - State
     - ``{contactfield=state}``
   * - State (Company)
     - ``{contactfield=companystate}``
   * - Subject
     - ``{subject}`` 
   * - Twitter
     - ``{contactfield=twitter}``
   * - Preferred Channel (Preference Center)
     - ``{preferredchannel}``
   * - Share Buttons
     - ``{sharebuttons}``
   * - Success Message
     - ``{successmessage}`` 
   * - Title
     - ``{contactfield=title}``
   * - Title (Landing Page)
     - ``{pagetitle}`` 
   * - Unsubscribe Text
     - ``{unsubscribe_text}``
   * - Unsubscribe URL
     - ``{unsubscribe_url}`` 
   * - Website
     - ``{contactfield=website}``
   * - Website (Company)
     - ``{contactfield=companywebsite}``
   * - Web View Text
     - ``{webview_text}`` 
   * - Web View URL
     - ``{{webview_url}`` 
   * - Zip Code
     - ``{contactfield=zipcode}``
   * - Zip Code (Company)
     - ``{contactfield=companyzipcode}`` 
  






