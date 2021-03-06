# Node.js

__Current versions: 0.4.12, 0.6.12 (03/17/12)__

Node.js is a non-blocking, evented I/O framework using the V8 JavaScript engine.

We host Node.js applications in their own VMs, which we call Node Machines. Cloudnode is based on the Nodester platform. During the beta stage, we may need to shut the service down for upgrades or service without notice. You should join our [discussion group](http://groups.google.com/group/cloudnode) to share any feedback and get important announcements that can affect running apps.

* [Preparing for deployment](#preparing)
* [Deploying to Cloudnode](#deploying)
* [Dependencies](#dependencies)

<a name="preparing"></a>
### Preparing for deployment

You can name the main file of your app like you want. Just make sure to specify that name, when you use the "create app" command. You can also specify any port you like as parameter to the listen function (in this sample port 8124). The platform will transparently override the parameter with the port of your Node VM which is in effect. 

    var http = require('http');
    http.createServer(function (req, res) {
      res.writeHead(200, {'Content-Type': 'text/plain'});
      res.end('Hello World\n');
    }).listen(8124, "127.0.0.1");
    console.log('Server running at http://127.0.0.1:8124/');

Whenever a port needs to be specified as a parameter for other function calls, use the environment variable "app_port" to use the port in use by your Node VM like in the following example:

    var webrepl = require('webrepl');
    var port = process.env["app_port"];

    webrepl.start(port);
    console.log("Web repl started (Listening on port " + port + ")");

<a name="deploying"></a>
### Deploying to Cloudnode

To create an app with the the Cloudnode command line use the following command:

    $ cloudnode app create <appname> <startfile> 
              - Creates a new app named <appname>, <startfile> is optional

Deployment is done with every Git push command. Additionally the application is restarted to active the changes introduced with the push command.

<a name="dependencies"></a>
### Dependencies

When your repository includes sub modules, these are also push to the Node Machine.