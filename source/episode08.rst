.. Copyright (C) Romin Irani. Permission is granted to copy, distribute
   and/or modify this document under the terms of the Creative Commons
   Attribution-ShareAlike 4.0 International Public License.


.. _web_activities:

Episode 8: Using Web Activities 
===============================

Welcome to Episode 8 of the Firefox OS App Development Tutorial. In the
previous episode, we looked at how you could add persistence to your
application via the IndexedDB API. In this episode, we shall use at Web
Activities, which as the official documentation states is a "way for
applications to delegate an activity to another (usually user-chosen )
application". 

Think of a simple example like making a phone call. This is standard
functionality that is available on the phone as part of the dialer application.
Now, lets say that you have a FirefoxOS Mobile App that at some point needs to
make a phone call. There is no need for you to understand the Telephony API and
try out some hair-raising stunts like that.

You know at the back of your mind that there is already a Dialer application
available. Similarly, if you need to send a SMS or an Email or even look up
Contacts, these applications are already present. So why not just launch those
in-built applications via a standard mechanism and offload the heavy-duty part
of the functionality to an application that already knows how to do it well.
That is the fundamental premise of a Web Activity.

You want to make a phone call in your application, just launch the Phone App.
You want to send a SMS in your application, just launch the SMS App. As simple
as that.


Prerequisites
-------------

* You have setup your machine with the Firefox OS Simulator.  If not you can
  check out :ref:`dev_setup`, which takes you through the entire setup.
* You have a basic understanding of writing Firefox OS Apps.  If not, I
  strongly suggest refering to earlier episodes, especially :ref:`hello_world`,
  that covers how to write your first Firefox OS App.


What this Episode covers 
------------------------

* `Web Activities
  <https://developer.mozilla.org/en-US/docs/Web/API/Web_Activities>`__ and whey
  they are important.
* Sample Firefox OS Application that covers using various Web Activities.


Episode 8 in Action
-------------------

Let us check out the application in action first to understand what we are
trying to do here.
