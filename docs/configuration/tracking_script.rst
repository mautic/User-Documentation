.. vale off

Tracking script
###############

.. vale on

After installation and setup of the :doc:`/configuration/cron_jobs` you're ready to begin tracking Contacts. You need to add a piece of JavaScript to the websites for each site you wish to track through Mautic.

This is straightforward process, you can add this tracking script to your website template file, or install a Mautic Integration for the more common Content Management System platforms.

Here is an example of the tracking JavaScript which you can access by clicking on **Tracking Settings** in the Global Configuration.


.. code-block:: javascript

  (function(w,d,t,u,n,a,m){w['MauticTrackingObject']=n;
     w[n]=w[n]||function(){(w[n].q=w[n].q||[]).push(arguments)},a=d.createElement(t),
     m=d.getElementsByTagName(t)[0];a.async=1;a.src=u;m.parentNode.insertBefore(a,m)
    })(window,document,'script','https://example.com/mautic/mtc.js','mt');
   mt('send', 'pageview');

You should replace the site URL, ``example.com/mautic`` with the URL to your Mautic instance in the example provided, but it's recommended to copy the whole code block from the tracking settings in your Mautic instance.