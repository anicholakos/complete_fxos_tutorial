.. Copyright (C) Romin Irani. Permission is granted to copy, distribute
   and/or modify this document under the terms of the Creative Commons
   Attribution-ShareAlike 4.0 International Public License.


.. _marketplace:

Episode 4: Submitting your Application to the Marketplace
=========================================================

Welcome to Episode 4 of the Firefox OS App Development Tutorial. This episode
will take you through the steps for submitting your Firefox OS App to the
Firefox Marketplace.


Prerequisites
-------------

* You have setup your machine with the Firefox OS Simulator.  If not you can
  check out :ref:`dev_setup`, which takes you through the entire setup.
* You have install the ``zipcodeapp`` that we covered in :ref:`hello_world`.
  This tutorial uses that as an example, but if you have any other application
  installed in the Firefox WebIDE, then you should be able to follow along. But
  I strongly suggest getting the `zipcodeapp source code from Github
  <https://github.com/jelkner/zipcodeapp>`__, and installing it as discussed
  in the previous episode.


What we shall cover in this Episode
-----------------------------------

* What is the Firefox Marketplace?
* Things you need to do before you consider submitting to the Marketplace.
* Additional files/materials you need before submission.
* Detailed steps to submitting the application and correcting errors along the
  way. 


Firefox Marketplace
-------------------

Smartphones are what they are today because of the applications that are
available on them. Each of the Smartphone OS has a Marketplace where developers
(individuals or organizations) can publish their applications for download by
users. The Applications can be free or paid.

The Firefox Marketplace is a similar ecosystem for the Firefox Family of
Applications. The Applications are not just restricted to Firefox OS Mobile
Applications but they also cater for Firefox Browser Add-ons, Firefox for
Android Apps, etc. The submission process is unified but we shall focus here on
submitting the application for availability on Firefox OS Device.

Few things to note in brief about the Firefox OS Marketplace so that you can
compare it against other similar offerings like Apple iTunes, Google Play, etc.

* Signing up for the Marketplace is Free. There is no yearly cost (like Apple
  iTunes) or one-time registration cost (Google Play).
* You can sell both free and paid applications. Selling Paid Applications
  would mean that you complete some additional paperwork.
* There is an application approval phase that is similar to what you see in
  Apple iTunes. Once your application is accepted after submission, it will be
  put in a "Pending Review" status and members from the Marketplace Review team
  will go through your application to certify that it is not doing anything it
  is not supposed to do :-) Once reviewed, it is available immediately or later
  on, if you decide otherwise.
* You can provide filters to your application that will ensure that the
  application is available for installation only on devices having features
  that you have asked for them to have. E.g. some Device APIs.
* The Firefox Marketplace App is available both as a
  `website <https://marketplace.firefox.com>`__ and also an application on the
  device. This is similar to other Smartphone OS.

The Firefox Marketplace (https://marketplace.firefox.com) as seen in your
desktop browser shown below:

.. image:: illustrations/episode01/fxos_marketplace.png
   :alt: Firefox Marketplace
   :height: 350px

The Firefox Marketplace App in your device is shown below:
