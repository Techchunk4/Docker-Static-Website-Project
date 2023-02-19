<h1>Docker statick website project.</h1>

<h4>
This project is a basic static website that is deployed using Docker containers. The project consists of a simple HTML webpage, a Dockerfile to build the container, and a Vagrant file to configure the virtual environment.
</h4>
<h2>Prerequisites:</h2>
<p>
Before starting with the project, ensure that you have the following installed:
</p>
<ul>
   <li>Docker</li>
   <li>Vagrant</li>
 </ul>
<h2>
Installation steps:
</h2>
<ol>
<li>Clone the repository to your local machine</li>
<li>Navigate to the root directory of the project in the terminal</li>
<li>Start the virtual machine using the following command:
vagrant up</li>
<li>SSH into the virtual machine using the following command:
vagrant ssh
</li>
<li>Navigate to the project directory:
cd /vagrant
</li>
<li>Build the Docker container using the Dockerfile:
docker build -t <image-name> .
Example: docker build -t my-static-website .
</li>
<li>Run the Docker container:
docker run -p <host-port>:80 <image-name>
Example: docker run -p 8080:80 my-static-website
Open a web browser and go to http://localhost:<host-port> to view the website.
</li>
</ol>
<h4>Conclusion:</h4>
<p>This project demonstrates how to deploy a simple static website using Docker containers. The Vagrant file provides a consistent virtual environment for development and testing.</p>
         






          
