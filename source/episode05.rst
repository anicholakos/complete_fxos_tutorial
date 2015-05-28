.. Copyright (C) Romin Irani. Permission is granted to copy, distribute
   and/or modify this document under the terms of the Creative Commons
   Attribution-ShareAlike 4.0 International Public License.


.. _locationlocation:

Location, Location, Location
============================

Welcome to Episode 5 of the Firefox OS App Development Tutorial. This episode
will take you through the steps for writing Firefox OS Apps that are location
aware. What this means is that your application can interact with the
`GPS receiver <http://en.wikipedia.org/wiki/GPS_navigation_device>`__
that is present on the Firefox OS Device, retrieve the current position
(`latitude <http://en.wikipedia.org/wiki/Latitude>`__, `longitude
<http://en.wikipedia.org/wiki/Longitude>`__) and thereby help you write
location based applications.


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


What this Episode covers 
------------------------

* What are Location Based Applications.
* HTML5 Geolocation API.
* Sample Firefox OS Application that covers using HTML5 Geolocation API.
* Sample Firefox OS Application that uses HTML5 Geolocation API to retrieve
  current position (latitude, longitude) and plot that on the Google Map. 


Episode 5 in Action
-------------------

Let us check out the application in action first. This will help you understand
what we shall be achieving by the end of this tutorial.

What we shall write is two mobile applications that will retrieve our current
position. On successfully getting the current position from the GPS receiver on
the Firefox OS phone, the first app will simply display the current longitude
and latitude, while the second app will plot that location on a map.

All right then, the first app, Locate Me, is shown below:

.. image:: illustrations/episode05/locateme3.png
   :alt: LocateMe app with location 
   :height: 350px

Here is the second app, Map Me:

.. image:: illustrations/episode05/mapme3.png
   :alt: MapMe app with location 
   :height: 350px
