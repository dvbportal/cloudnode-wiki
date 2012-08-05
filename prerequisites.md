# Prerequisites

Since Cloudnode is a cloud hosting environment, your app must conform to a couple different requirements and prerequisites in order to run on it. By following these best practices in app architecture and design, you can ensure that your app will run well on the Cloudnode platform.

* <a href="#required-software">Required Software</a>
* <a href="#best-practices">Best Practices</a>
* <a href="#read-only-filesystem">Read-only Filesystem</a>
* <a href="#logs">Logs</a>
* <a href="#dependency-management">Dependency Management</a>
* <a href="#app-initialization">App Initialization</a>
* <a href="#git">Git</a>

<a name="required-software"></a>
## Required Software

The workflow used to develop and deploy apps on Cloudnode depends on Git, Node.JS, npm and our command line client, which in fact is a node app itself. The tools are available for all major OS'es. See the following links

* git - <span class="external"><http://git-scm.com/></span> - The distributed version control system
* node.js - <span class="external"><http://nodejs.org></span> - The node server
* npm - <span class="external"><http://npmjs.org/></span> - The Node Package Manager
* cloudnode - __npm install cloudnode-cli -g__ - The  [Cloudnode command line](/cloudnode-command-line)

<a name="best-practices"></a>
## Best Practices

Take care to keep the size of your app small.

Do not include large files (documents, media files, data files, etc.) in your app. These should be hosted on an outside asset store such as Amazon S3.

Only include modules that you will use.

### Sensitive data and passwords ###
 
Make sure to keep sensitive data outside of your code because the repositories are public. It is recommended to store sensitive data using [environment variables](/api#env). 

<a name="read-only-filesystem"></a>
## Read-only Filesystem

Cloudnode apps are not able to write to file filesystem in general. However there are a couple special locations to which you can write files.

### Cloud storage (/mnt)

All Cloudnode apps have access to limited persistent file storage under /mnt. Cloud storage is persistent between requests and app instances.

Cloud storage is designed to store files generated from within your app (e.g. generated stylesheets or asset packages). See [Cloud Storage](/cloud-storage) for details.

### Temporary files (/tmp)

The /tmp directory in your app root is writeable (for files of reasonable size), but anything written to it should not be expected to endure over hours.

<a name="logs"></a>
## Logs

Logs on the Cloudnode platform should be considered transient. It is possible to tail the last 100 lines through the command line.

See [Troubleshooting](/troubleshooting) for full details.

<a name="dependency-management"></a>
## Dependency Management

If your app depends on any npm packages, they need to be installed into your Node VM. See [Node package manager](/node-package-manager) for details.

<a name="app-initialization"></a>
## App Initialization

Node looks for a startup file normally called __server.js__ to boot your application. You can choose a different file and directory, when you create the application. For details see the [Cloudnode command line](/cloudnode-command-line).

<a name="git"></a>
## Git

<span class="external">[Git](http://git-scm.com)</span> is the only way to push code to Cloudnode for deployment. This means your app must be part of a Git repository. You don’t necessarily need to use Git for version control during development, but when it comes time to deploy to Cloudnode, your app code does need to be committed to a Git repo.

Deployment is as easy as __git push origin master__. See the [Quick Start Guide](/quick-start-guide) for more details.

For additional help on using Git see the excellent help files at GitHub especially the setup and troubleshooting guides when using ssh key and key phrases: <span class="external"><http://help.github.com/></span>


### Git Submodules

Git submodules are supported on the Cloudnode platform.