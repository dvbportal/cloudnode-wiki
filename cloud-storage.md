# Cloud Storage

Every Node application on Cloudnode runs in a [virtual machine](node-vm) with its own disk storage. The disk holds a full checkout of the application's [Git](/git) repository. So you have access to modules sub-modules and static resources, you have checked in. The disk also holds all Node modules you have installed using the [npm](/node-package-manager) command and a minimum set of directories to get Linux running like __/etc__.

### Special Directories

You should not assume, that there is write access to the disk except to the __/mnt__ and __/tmp__ directories. Your application can use these directories to store dynamic data. As the names suggest, __/tmp__ can be used to store volatile files and __/mnt__ can be used to store permanent files. These will always "follow" your application and be mounted at __/mnt__.