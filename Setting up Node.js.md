 How to Install Latest Node.js and NPM on Ubuntu with PPA
 ========================================================
##### Written by Rahul, Updated on March 19, 2019
Nodejs node, node.js, nodejs, npm, Ubuntu

Node.js is a platform built on Chrome’s JavaScript runtime for easily building fast, scalable network applications. Latest version node.js ppa is maintaining by its official website. We can add this PPA to your Ubuntu 19.04, 18.04 LTS, 16.04 LTS (Trusty Tahr) and 14.04 LTS (Xenial Xerus) systems and install node.js on Linux VPS with easy commands.

To install specific nodejs version, Visit our tutorial Install Specific Nodejs Version with NVM.

Install latest node.js
Step 1 – Add Node.js PPA

Node.js package is available in LTS release and the current release. It’s your choice to select which version you want to install on the system as per your requirements. Let’s add the PPA to your system to install Nodejs on Ubuntu.

Use Current Release: At te last update of this tutorial, Node.js 11.12.0 is the current Node.js release available.

```sudo apt-get install curl python-software-properties
curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -
```

Use LTS Release : At the last update of this tutorial, Node.js 10.15.3 is the LTS release available.

```sudo apt-get install curl python-software-properties
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
```
For this tutorial, I am using the latest current release and added their PPA to my system.
Step 2 – Install Node.js on Ubuntu

You can successfully add Node.js PPA to Ubuntu system. Now execute the below command install Node on and Ubuntu using apt-get. This will also installed NPM with node.js. This command also installs many other dependent packages on your system.

```sudo apt-get install nodejs
```

Step 3 – Check Node.js and NPM Version

After installing node.js verify and check the installed version. You can find more details about current version on node.js official website.

```node -v
``` 

v11.12.0

Also, check the npm version

```npm -v 
```
6.7.0

Step 4 – Create Demo Web Server (Optional)

This is an optional step. If you want to test your node.js install. Let’s create a web server with “Hello World!” text. Create a file server.js

```vim server.js
```

and add the following content
```server.js

var http = require('http');
http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello World\n');
}).listen(3000, "127.0.0.1");
console.log('Server running at http://127.0.0.1:3000/');
```
Now start the Node application using the command.

```node server.js
```
```
debugger listening on port 5858
Server running at http://127.0.0.1:3000/
```
You can also start the application with debugging enabled with the following commands.

```node --inspect server.js
```

Debugger listening on ws://127.0.0.1:9229/8976a32b-cf99-457c-85fb-e7288cbadac6
For help see https://nodejs.org/en/docs/inspector
Server running at http://127.0.0.1:3000/

The web server has been started on port 3000. Now access http://127.0.0.1:3000/ URL in browser. Now you will need to configure a front-end server for your app.

    Read: How to Setup Nginx as Frontend Server for Node.js