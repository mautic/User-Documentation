
Companies
#########

Companies are a way to group Contacts based on association with organizations.

.. image:: images/Mautic-31-company-view.png
  :width: 600
  :alt: Mautic Company Overview
  
Engagements/Points chart
***********************

Engagements shown on the chart include any tracked action the Contacts made. Some examples might include page hits, Form submissions, Email opens and so on. The engagements line chart displays how active the Contacts of the Company were in the past 6 months. The chart displays also the sum of Points the Contacts received.

.. vale off

List of Contacts assigned
*************************

.. vale on

You can find a table with the list of the assigned Contacts displaying the date of their last activity, preceding the information of the Company which includes the Company name, address, and all the custom Company fields, and the engagement chart. This is good way to have a view of the recent activity of the Contacts you know in this Company.

Company duplicates
*******************
The Company name field is a unique identifier by default. You can choose any other Company field as unique identifier in the **Custom Fields** section.

In *Configuration > Company Settings* you can choose the operator used when merging Companies with multiple identifiers - either **AND** or **OR**.

.. image:: images/company-duplicates-configuration-operator.png
  :width: 600
  :alt: Setup operator for find duplications algorithm

These settings allow  Mautic to find and merge duplicate Companies during the import, using the Integrations Framework and in other parts of Mautic.

Company actions
***************

.. vale off 

Merging Companies
=================

.. vale on

When editing a Company, you can merge this Company into another existing Company by using the **Merge** button.

Search for the Company you wish to merge into, then click to start the merge. Contacts associated with the merged Companies now become associated with the remaining Company.

After completion of the merge process, Mautic redirects you to the remaining Company, as the old Company no longer exists.

.. vale off

Company Custom Fields
*********************

.. vale on

By default, a set of fields exist for Companies, but you can customize these fields to meet your needs.

#. Go to **Custom Fields** and create a new field
 
#. Change the dropdown select box from Contact to Company objects

#. Save the Custom Field

.. vale off

Company Segments
****************

.. vale on

You can create a Segment based on a Company record. Select any Company field to filter with and the matching criteria for it, and Mautic lists any Contacts that match the selected fields in the Segment.

.. vale off

Identifying Companies
*********************

.. vale on

Mautic identifies Companies strictly through a matching criteria based on **Company Name**, **City**, **Country or State**. If  a city or a country isn't delivered as an identifying fields to identify a Contact, the Company won't match.

.. vale off

Company actions in Campaigns
****************************

.. vale on

It's possible to add a Contact to a new Company based on a Campaign action.

.. vale off

Creating and managing Companies
*******************************

.. vale on

To create or manage Companies, go to the Companies menu identified by the building icon in the left hand navigation. In this area you can create, edit, or delete Companies.

.. vale off

Assigning Companies to Contacts
*******************************

.. vale on

There are different ways to assign a Company to a Contact as explained below:

Contact profile
===============

You can assign a Contact to Companies in the Contact's profile, while creating or editing an existing Contact. Mautic considers the latest Company assigned as the primary Company for the Contact.

Contacts list view
==================

You can batch assign Companies to selected Contacts in the Contact's list view.

.. vale off

Via a Campaign
==============

.. vale on

You can assign a Company to identify Contacts through a Campaign by selecting the **Assign Contact to Company** action.

.. vale off

Through a Form
==============

.. vale on

When identifying a Contact through a Form, you can also associate an existing Company or create a new one if:

- The Form includes Company name as a Form Field - mandatory for Company matching/creation,
- The Form includes City as a Form Field - mandatory for Company matching/creation,
- The Form includes Country as a Form Field - mandatory for Company matching/creation,
- The Form includes State as a Form Field - optional for Company matching/creation.
  
Company scoring
================

It's possible to change the Company score through a Campaign action or a Form action. When using these actions, it's necessary to identify the Contact first, and then alter the score of the Companies assigned to that Contact.

#. Select the **Change Company score** action in either a Form or a Campaign
#. Once submitted or triggered, Mautic identifies Companies in the Campaign or Form to change their score.

.. vale off

Setting the primary Company
===========================

.. vale on

You can set the primary Company through the Contact details interface.

.. image:: images/primary-company.png
  :width: 600
  :alt: Screenshot showing setting the primary Company

