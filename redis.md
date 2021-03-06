# Redis

The Cloudnode platform offers fully managed, hosted Redis instances for your Node.js apps. <span class="external">[Redis](http://redis.io)</span> is an open source, advanced key-value store. It works out-of-the-box with Express and many other Node.js apps and modules. The database instances are on a fast local network connection and offer superior speed compared to other hosted solutions.

### Redis Administration

The "My Databases" tab lists your databases. From here you can also control your instances, create new Redis instances and delete existing ones. Clicking on a database name opens the detail page, where you find your authorization code and port number to access the Redis instance. From here you can also access log and configuration files and manage the instance.

### Redis Authorization

Your app's environment is populated with variables that contain all data needed to access the Redis Database. Tot do so select the Redis database during application creation. The environment will receive the following variables:

* redis_port="port number"
* redis_auth="autorization code"

You can check these values from the "Manage App" screen by clicking "Get Env".

### Usage Example 

The preferred client package to access Redis is <span class="external">[node_redis](https://github.com/mranney/node_redis)</span> by mranney. It comes with docs and samples. 
