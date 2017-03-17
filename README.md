# iframe-replacestate-backbutton


Overview
=============

Demonstrates a local page embedding a remove iframe resource, and how that iframe uses the replaceState on 
the history object to avoid the browser back button from loading a posted page. 

Setup
=============

* You will need a http server to point to the project location, use alias "/frame-demo"
* You will need to make a host file entry for a remote host, use "127.0.0.1 notlocalhost.com"

Demo Flow
=============

The overall flow is to have a local page that hosts a remote iFrame, that remote iFrame will post 
back to the local page with it's results when done, we want to avoid the iFrame's history from incorrectly
loading into itself and giving the customer a bad experience. The demo page names are named for 
payment, but this can be used for anything

![alt tag](https://raw.githubusercontent.com/tepietrondi/iframe-replacestate-backbutton/master/Screen%20Shot%202017-03-17%20at%2011.25.54%20AM.png)

Page 99 - Remote
-------
* This page is the remote landing page for reporting not to use the back button

Page 00 - Local
-------
* This page is the locally hosted page that will embed the iFrame
* The iFrame is loaded via JS to simulate a delay, note the iFrame is remote, on an alternate domain

Page 01 - Remote
-------
* This page is remote, it hosts the form entry that will be posted to a processing page
* On submit, it will replace the history with the no back button page

Page 03 - Local
-------
* This page is local, it hosts the post back complete message

Running the demo
-------
* Point browser to http://localhost/frame-demo/00_local_index.html
* 00 will load and embed 01
* Now submit the form embedded in the page
* 01 will post to 02 and post to 03
* Now click the browser back button, the customer should see page 99 embedded

Reference 
=============

* https://developer.mozilla.org/en-US/docs/Web/API/History_API
* http://www.webdeveasy.com/back-button-behavior-on-a-page-with-an-iframe/
* https://blog.twitter.com/2012/implementing-pushstate-for-twittercom
* https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onpopstate

