.. Copyright (C) Romin Irani. Permission is granted to copy, distribute
   and/or modify this document under the terms of the Creative Commons
   Attribution-ShareAlike 4.0 International Public License.


.. _mbaas:

Episode 10: Using mBaaS
=======================

Welcome to Episode 10 of the Firefox OS App Developent Tutorial. In the
previous episode, we looked at how you can use Device Storage in your Firefox
OS Applications.

In this episode, we shall be taking a look at an emerging area known as Mobile
Backend As a Service (mBaaS). The idea is that we shall be powered our Firefox
OS Application from Server side infrastructure and functionality that shall be
provided by the mBaaS Provider.

What we shall be doing is writing a Random Quotes Firefox OS Application. The
Quotes are those said by famous men over the years. For e.g. Albert Einstein
said "The difference between stupidity and genius, is that genius has its
limits" and so on. All these quotes will not be present locally in the Firefox
OS App local storage or database, it will in fact be delivered from a Server
side solution.  This will make it easier for us to update the Server side with
data whenever we want.


Prerequisites
-------------

* You have setup your machine with the Firefox OS Simulator.  If not you can
  check out :ref:`dev_setup`, which takes you through the entire setup.
* You have a basic understanding of writing Firefox OS Apps.  If not, I
  strongly suggest refering to earlier episodes, especially :ref:`hello_world`,
  that covers how to write your first Firefox OS App.


What this Episode covers 
------------------------

* What is `mBaaS
  <http://en.wikipedia.org/wiki/Mobile_Backend_as_a_service>`__, and
  why it is important. Discussion of
  `Kinvey <http://www.kinvey.com>`__, a leading mBaaS provider.
* Sample Firefox OS Application that demonstrates integration with
  Kinvey. In other words, our Firefox OS application will be powered by Kinvey. 


Episode 10 in Action
--------------------

Let us check out the application in action first to understand what we are
trying to do here.
