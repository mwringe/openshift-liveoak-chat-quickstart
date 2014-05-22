#LiveOak Chat QuickStart

This Openshift QuickStart will install the LiveOak Chat example.

Documentation for the Chat example can be found here:

https://github.com/liveoak-io/liveoak-examples/tree/master/chat/chat-html

#Instruction

To install the quick start from the 'rhc' tool:

```
rhc app create myChatApp diy --from-code git://github.com/liveoak/openshift-liveoak-chat-quickstart
```

or install from the openshift console using the DIY cartridge with the source code option set to git://github.com/liveoak/openshift-liveoak-chat-quickstart 


This example assumes that you have your LiveOak instance running on a gear under your same account called 'liveoak'. If you have your liveoak instance running on another machine, please edit the diy/chat.js.erb file to modify the host and or port to point to the LiveOak instance you want to use.

For example, if your LiveOak is running on a site called 'myAwesomeMBaaS.com' on port 80, you would modify the following line in diy/chat.js.erb from

```
var liveoak = new LiveOak( { host: "liveoak-<%= ENV['OPENSHIFT_NAMESPACE'] %>.<%= ENV['OPENSHIFT_CLOUD_DOMAIN'] %>", port: 8000 } );
```

to 

```
var liveoak = new LiveOak( { host: "myAwesomeMBaaS", port: 80 } );
```

This example also assumes that you have 'chat-html' application setup in your LiveOak instance. To setup your 'chat-html' application in LiveOak:

* Log into the console

* Click 'Create Application'

* name your application 'chat-html'

* keep the type of setup as 'basic', click 'Next'

* keep the default storage name as 'storage', click 'Next'

* leave the UPS data empty, and click 'Create Application'

Thats it, now open up the gear running the example and you should be able to see the html chat example loaded.
