# Node VM

Node Virtual Machines are the fundamental building blocks of the Cloudnode infrastructure. A Node VM represents the hardware resources a Node App can access, including the CPU, the network, disk storage and database storage. Each Node App is an OS process running on the Cloudnode platform and serving request from its users. Each VM can be individually started and stopped. Stopped Node VMs release resources and make them available to other VMs.

### Isolation

While several Node VMs can share physical resources, they remain completely isolated from each other. Each Node VM has a fully virtualized read-only disk which provides the necessary infrastructure. Two read/write directories /tmp and /log can be used to store volatile data during the runtime of the Node VM. All console and standard output is writen to the /log directory and can be accessed using the [Cloudnode command line](/cloudnode-command-line).

The /mnt directory can be used to store files that persist during start/stop cycles of the VM.

### Compatibility   

Each Node VM provides a standardized environment, so that a Node App can be run unmodified on the Cloudnode platform as on any other platform that offers a Node.js environment.    

### Instance Management

The Cloudnode [API](/api) allows it to query and control the running state of each Node VM. To check the running state using the [Cloudnode command line](/cloudnode-command-line) use the following command:

    $ cloudnode app info <appname>

    cloudnode info Checking config..
    cloudnode info Gathering information about: <appname>
    cloudnode info <appname> on port <port> running: true
    cloudnode info gitrepo: cloudnode@git.cloudno.de:<repo addr>
    cloudnode info appfile: demo/server.js


To start or stop the App and its Node VM use the start/stop/restart command:

    $ cloudnode app stop <appname>

    cloudnode info Checking config..
    cloudnode info Attemping to stop app: <appname>
    cloudnode info app stopped.


You can also use the API directly or use the web frontend.