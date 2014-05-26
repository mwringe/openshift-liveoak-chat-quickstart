#LiveOak Chat Example QuickStart

This OpenShift QuickStart will create and configure a DIY gear to host the LiveOak Chat example's HTML 5 client side code. It will requires access to a LiveOak instance already configured for the chat example's backend logic.

For more information on how to configure a LiveOak gear in OpenShift with the example's backend already configured, please refer to the following quickstart:

https://github.com/liveoak-io/openshift-liveoak-examples-quickstart

Or refer it its application.json file available [here] (TODO: insert link here)

The Chat example showcases real time push notifications on resource modifications and storage of data to a MongoDB database within LiveOak.

If you wish to run the Chat example locally on your own machine, please see the  example available here:

https://github.com/liveoak-io/liveoak-examples/tree/master/chat/chat-html

#Installing the Gallery Client Example

To install the quick start from the 'rhc' tool:

```
rhc app create myChatApp diy --from-code git://github.com/liveoak/openshift-liveoak-client-chat-quickstart
```

or install from the OpenShift console using the DIY cartridge with the source code option set to git://github.com/liveoak/openshift-liveoak-client-chat-quickstart 


This example assumes that you have your LiveOak instance running on a gear under your same account called 'liveoak'. If you have your liveoak instance running on another machine, please edit the diy/chat.js.erb file to modify the host and or port to point to the LiveOak instance you want to use.

For example, if your LiveOak is running on a site called 'myAwesomeMBaaS.com' on port 80, you would modify the following line in diy/chat.js.erb from

```
var liveoak = new LiveOak( { host: "liveoak-<%= ENV['OPENSHIFT_NAMESPACE'] %>.<%= ENV['OPENSHIFT_CLOUD_DOMAIN'] %>", port: 8000 } );
```

to 

```
var liveoak = new LiveOak( { host: "myAwesomeMBaaS", port: 80 } );
```

#Configuring the Gallery Client Example

The following steps assume that you have not already configured your LiveOak instance for the examples yet. If you have installed your LiveOak gear with the example quickstarts, you will not need to follow the following steps as they have been performed as part of the quickstart.

If you have not already setup your LiveOak instance for the 'chat-html' example, you can do so by performing the following steps to configure it:

* Log into the LiveOak console

* Click 'Create Application'

* name your application 'chat-html'

* keep the type of setup as 'basic', click 'Next'

* keep the default storage name as 'storage', click 'Next'

* leave the UPS data empty, and click 'Create Application'

That's it for configuring this example.

#Accessing the Gallery Client

After you your gear has been created, you should be presented with a link to access the website. Accessing the website will take you to the chat example, which allows you to send and receive chats in real time. Note that this is an open chat application, all the chats and correspondence is public. 
