# Read-05:

------------
## Node.js:
 - is an open source, cross-platform runtime environment, which allows you to build server-side and networking applications.
 
- To access node.js file : By typing (node server.js)in the terminal.
-  Node allows you to use the so-called event loop, which works faster because of non-blocking behavior.
------------
## Heroku:
-  We'll use Heroku cloud application platform for this. Heroku is a cloud platform as a service
- It allows you to deploy your web server, so everyone could see how awesome you are as a web developer.
- After finish intalling :
1. to log in : type in the terminal (heroku login).

2. declare some variables:

var http = require("http");
var fs = require("fs");
var path = require("path");
var mime = require("mime");

  - The first one will give you the key to Node's HTTP functionality.
  - The second one is for possibility to interact with the file system.
  - The third one allows you to handle file paths.
  - The last one allows you to determine a file's MIME-type.
  
3. Create the package.json file:  
  - We need to create the package.json file for that purpose.
  - It will contain project related information, such as name, version, description.
  - EX: 
    - {
  "name" : "blog",
  "version" : "0.0.1",
  "description" : "My minimalistic blog",
  "dependencies" : {
    "mime" : "~1.2.7"
  }
}

4. RUN : (npm install); It will create node_modules folder and place all the files inside of it.
5. create send404() function :It will handle the sending of 404 error, which usually appears when requested file doesn't exist.
  - EX: function send404(response) {
  response.writeHead(404, {"Content-type" : "text/plain"});
  response.write("Error 404: resource not found");
  response.end();
}

6. define sendPage() function: It first writes the header and then sends the contents of the file.
  - EX : function sendPage(response, filePath, fileContents) {
  response.writeHead(200, {"Content-type" : mime.lookup(path.basename(filePath))});
  response.end(fileContents);
}

7. define how our server will handle responses: 
  - This function will return the content of the requested file or the 404 error otherwise.
  - EX : function serverWorking(response, absPath) {
  fs.exists(absPath, function(exists) {
    if (exists) {
      fs.readFile(absPath, function(err, data) {
        if (err) {
          send404(response)
        } else {
          sendPage(response, absPath, data);
        }
      });
    } else {
      send404(response);
    }
  });
}

8.  create the HTTP server :
  - var server = http.createServer(function(request, response) {
  var filePath = false;

  if (request.url == '/') {
    filePath = "public/index.html";
  } else {
    filePath = "public" + request.url;
  }

  var absPath = "./" + filePath;
  serverWorking(response, absPath);
});


9. start our server:
   -http.createServer(<some code here>).listen(3000).
   
10. create the index.html file :
  -It will determine our blog's exterior. 
  
11. To start your server locally run:(node server.js)
12. to deploy our server :
   1. Open your terminal within your project folder:
    -cd /path/to/my/project
    
   2. Then run:
     git init
     
   3. To initialized Empty Git repository in .git/ folder:Then run:
     git add .
     
   4. commit your files to the initialized Git repo:
    git commit -m "Simple server functionality added" 
    
  5. create our  Heroku application:
    heroku create
    
  6. first time we deploy our project, we need to specify a remote branch to push to:
    git push heroku master
    heroku ps:scale web=1
  
  7. choose a proper name for our first creation. I called it myfirstserver:
    heroku apps:rename myfirstserver
    
  8. Everything is done. You can try it now:
    heroku open
    
    
    -------------
    - DIRT. It means Data-Intensive Real-Time applications. Node allows a server to handle a lot of connections and work with a number of requests at the same time. 
    And you don't need much memory for that. It's designed to be responsive and fast. 
    - it's useful when you need to create an application that will be able to respond instantly to a large number of users.
     And Node was built from scratch to provide you with such a functionality.
