# harsh_flask_web_app_docker

DEPLOYING A CONTAINERIZED FLASK BASED WEB APPLICATION ON DOCKER.

A simple Flask application where we will be publishing a webpage using Dockerfile, Images, Containers and Flask tools & libraries as a framework. 

CODE BREAKUP:
- “flask” is the framework here, while “Flask” is a Python class datatype. In short, Flask  is the prototype used to create instances of web application.
- Once we import Flask, we need to create an instance of the Flask class for the web app. That’s what next line does. 
- “_ _name_ _” is a special variable that gets as value string ”_ _main_ _" when you’re executing the script. We’ll go back to that in a moment.
- Next, a function “myfirst_webapp” is defined which checks Flask’s-function “render_template” to return the HTML template “docker.html” and it is mapped to the home ‘/’ which means when the user will open the URL: localhost:8081, the home function will run and it will return its output on the webpage.
- Since, Python file or module is running as a main program, hence, _ _name_ _ variable will be set as “_ _main_ _” otherwise if the code is importing the module from another module, then the _ _name_ _ variable will be set to that module’s name.
- Last, set “debug = true” which will print out possible Python errors on the web page so that errors can be traced. Also, Host IP is set to 0.0.0.0 (localhost) and host port is set to 8081.


Once done with all the pre-requisites steps including the Dockerfile, its time to build our image from that file. Make sure that you are in the directory parent directory. 

To create a docker image, you have to run the following command:

 $ docker build –t  mywebapp-flask:latest  .

Just like when pulling images from Dockerhub, this command tells the Docker engine to create a repository named “mywebapp-flask” and tag it with “latest” using –t. You can apply multiple tags to an image.

Don’t forget to put “dot operator” at the end as it specifies the current directory.

Next step is to containerized this image and run it, you have to execute the below command:
  $ docker run -d -p  --name [container name]  [image ID or name]
  
-d : Runs the container in background and print container ID; 
-p : By this you can publish the container's port to the local machine. I’ve used port 8081 - this will allow us to go to http://localhost:8081 on our machine & view the container’s response on that same port; 
--name : Assign a name to the container.

Note: 8081:8081 = Host Machine Port : Container Port. (you can use any random port). Also 0.0.0.0 means local host machine. To see the port binding between the host machine and the container, you can run command:  $ docker inspect [Container name or ID]

Last step is to access the web-browser and open link - http://localhost:8081




