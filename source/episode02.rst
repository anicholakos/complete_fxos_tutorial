.. Copyright (C) Romin Irani. Permission is granted to copy, distribute
   and/or modify this document under the terms of the Creative Commons
   Attribution-ShareAlike 4.0 International Public License.

.. _hello_world:

Hello World
===========

Prerequisites
-------------

You have setup your machine with the Firefox OS Simulator. If not, you can go
back to :ref:`dev_setup` to do this.


.. index:: hosted apps, packaged apps, apps; hosted, apps; packaged

Brief Overview of Firefox OS Apps
---------------------------------

Firefox OS supports 2 kinds of applications: **Hosted Apps** and
**Packaged Apps**.

**Hosted Apps** are those that are hosted at a web url. All the files that
compose the app i.e. HTML, JS, CSS, images, etc are all present at the hosted
url itself. No file is present on the device and the device will need to be
connected to the internet to use it. There are mechanisms now in HTML5 like
AppCache that allow you to cache assets of the file locally though for most
purposes, we will assume that hosted apps are completely present online.

The advantage of hosted apps is that you can update them easily and all your
users will get the latest version immediately on next access. The flip side is
that they have to be connected.

**Packaged Apps** take the opposite approach. All the files that compose your
web app i.e. HTML, JS, CSS, images, etc are packaged into a ZIP file. The ZIP
file is downloaded on your device and the app is installed locally.
Applications that are deployed in this fashion can function without the device
being connected to the internet. However, if your application makes use of some
public API or external web service, you will need to be connected.

The Firefox Marketplace which we shall see in a later episode supports listing
of both Hosted and Packaged Applications.


.. index:: ajax, API

Episode 2 in Action
-------------------

Let us check out the application in action first. This will help you understand
what we shall be achieving by the end of this blog post. While we follow
tradition and would like to say “Hello World”, it will be good to go a bit
beyond that.

What we shall write is a mobile application that will give us details on the
different Pincodes in India. Pincodes are similar to Zipcodes if you want an
analogy. You enter a valid Pincode in the application and it will give you the
details of that Pincode i.e. its State name, District Name, etc.

The mobile application makes use of an external Web service called `Zip Code
Galore! <http://api.zippopotam.us>`__. This will also help demonstrate making
Ajax calls over the network from your Firefox OS Mobile. Nothing special there
but by taking a little more realistic example, it will help set off things on
the right note.

All right then, the first screen of the mobile app is shown below:

.. image:: illustrations/episode02/app_in_action1.png
   :alt: App before entering pin code 
   :height: 350px

When we enter a valid pincode e.g. **20001**, the app makes a call to the
ZIP code service and retrieves/parses/displays the information as shown below:

.. image:: illustrations/episode02/app_in_action2.png
   :alt: App after submitting pin code 
   :height: 350px

Simple and useful? Let’s get going with the code. Note that the example
screenshots are from the Firefox OS Simulator running locally.


Download Full Source Code – Episode 2
-------------------------------------

I suggest that you begin with a full download of the project source code. Since 
the project depends on libraries like jQuery and jQuery Mobile, it will save
you the hassle of downloading the dependent libraries.

Go ahead and download the code from: `https://github.com/jelkner/zipcodeapp
<https://github.com/jelkner/zipcodeapp>`__

Extract all the code in some folder. For e.g. on my machine, the code is
present in ``$HOME/Projects/zipcodeapp`` but it could be any directory of your
choice. You should see a folder structure inside of ``zipcodeapp``, that looks
like this:

.. image:: illustrations/episode02/folder_structure.png
   :alt: App folder structure 
   :height: 300px

You will notice that ``jQuery`` and ``jQueryMobile`` libraries are present but
the key files that make up your application are ``index.html``, ``zipcode.js``,
and the ``manifest.webapp`` files that we shall discuss next.


.. index:: index.html, UI, user interface

The UI  – index.html
--------------------

Since our application is a simple single screen application, all we need at
this point is a single ``index.html`` file together with the ``zipcode.js``
file that contains the programming logic. The code for ``index.html`` is shown
below:

.. literalinclude:: _static/episode02/index.html
   :language: html
   :linenos:

The UI is based on `jQuery Mobile <https://jquerymobile.com/>`__, which is a
responsive web UI framework. I strongly suggest to use UI frameworks that are
responsive in nature i.e. they adapt to different screen sizes and resolutions.
Increasingly the web is being accessed by people with different screen sizes
and resolutions and it is imperative that your web UI adjust itself gracefully
for optimum web display.  You can also choose to go for frameworks like
`Bootstrap <http://getbootstrap.com/>`__ or even `Firefox OS Building Blocks
<https://developer.mozilla.org/en-US/Apps/Design/Firefox_OS_building_blocks>`__,
but I leave that choice to you.

One point to note here: One may argue about why a simple application like this
needs heavy frameworks like jQuery and jQuery Mobile. Can’t we just get going
with our plain simple HTML coded by hand. Yes you can. My intention here is not
to demonstrate optimum coding techniques but to show you that you can use your
existing frameworks while coding Firefox OS apps. The idea is to indicate to
the reader that all the tools/frameworks that he/she is used to should be used
as needed.

So moving on to the UI part, focus on lines 14-30 for the user interface.

* **Line 21** declares the input field that we shall use to allow for the user
  to enter the pincode. Note that we make good use of HTML5 attributes like
  placeholder and autofocus. The placeholder attribute is a good way to specify
  what needs to be entered in the input (like a hint). It saves a lot of real
  estate on a small mobile screen.
* Do note that the ``inputtype`` is also specified as ``search``. This is a
  very useful attribute on mobile screens. It will allow for a quick way to
  clear up the input as you type text.
* If you want to brush up on HTML Form Features and input types, check out my
  blog posts: `HTML5 Recipes: Forms Enhancements
  <http://rominirani.com/html5-recipes-forms-enhancements/>`__ and `HTML5
  Recipes: New Input Types
  <http://rominirani.com/html5-recipes-new-input-types/>`__.
* **Line 23** specifies a button labeled ``Search``, which when clicked needs
  to retrieve for us the details of the ZIP code entered.
* **Lines 25-27** define the results list where we shall display the results.
  This is just my way of definining the UI. Feel free to be as creative as you
  want.


The code - ``zipcode.js``
-------------------------

.. literalinclude:: _static/episode02/zipcode.js
   :language: javascript 
   :linenos:


Manifest file - ``manifest.webapp`` 
-----------------------------------

Now that the code is ready, we need to specify an additional file known as
``manifest.webapp``. This file is needed to provide various meta data about
your application. If you are coming from an Android world, think of this file
as the ``android-manifest.xml`` file that you write.

We shall go into the details on manifest in a later episode but for now, it is
sufficient to know that this file will provide information like:

* Name of your App
* App Version
* App Description
* App Icons
* Permissions that your app needs to run on device
* Locales that your App supports
* and much more

Take a look at the ``manifest.webapp`` file shown below:

.. literalinclude:: _static/episode02/manifest.webapp
   :language: javascript 
   :linenos:

Let us discuss the entries:

* The **version**, **name** and **description** should be straightforward to
  understand. A good practice is to choose them carefully so that they reflect
  accurately what your application does. Choose a versioning scheme that
  reflects your internal schemes and/or development/build processes.
* The **launch_path** specifies what file is to be invoked when your app is
  launched. This is ideally the first page that you would like to show when the
  user launches your app. The value should be a relative path in your
  application directory. In our case, the file we want to launch on application
  start is ``index.html`` and since the ``manifest.webapp`` file is in the same
  folder as the ``index.html``, so we simply specify the value as
  ``/index.html``.  But make it a relative path in case the first page is
  nested inside some other directory than where the ``manifest.webapp`` is
  present.
* When your mobile application is installed on the Firefox OS Device, the OS
  will select the icon to be shown on the device, which when tapped will launch
  your application. To submit an app to the marketplace, it is required to have
  two sizes of icons: 128 pixel and 512 pixel (see
  `https://developer.mozilla.org/en-US/Apps/Build/Manifest
  <https://developer.mozilla.org/en-US/Apps/Build/Manifest>`__).
* The next values **developer**, **url** and **name** specify details on who
  created the application. Be consistent with these values and do specify a url
  that actually exists.
* The **default_locale** is English (en) for now.
