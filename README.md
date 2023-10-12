To create a Dockerfile for a static website using a Virtual Machine and Vagrant, you'll need to perform a few steps. First, you'll create a Dockerfile to define the container's environment, and then you'll use Vagrant to manage the VM and deploy the Docker container. Here's a basic example:

1. Create a directory for your project and navigate into it:

```bash
mkdir my-static-website
cd my-static-website
```

2. Create a Dockerfile (Dockerfile) in the project directory with the following content:

```Dockerfile
# Use an official Nginx runtime as the base image
FROM nginx:latest

# Remove the default Nginx configuration
RUN rm /etc/nginx/conf.d/default.conf

# Copy your static website files to the Nginx HTML directory
COPY ./website /usr/share/nginx/html

# Expose port 80 for the web server
EXPOSE 80

# Start the Nginx web server
CMD ["nginx", "-g", "daemon off;"]
```

3. Create a "website" directory inside your project folder and place your static website files (HTML, CSS, JS, etc.) inside it.

4. Now, let's set up Vagrant to manage the VM and deploy the Docker container. Create a Vagrantfile in the project directory with the following content:

```ruby
Vagrant.configure("2") do |config|
  # Use a suitable base box, e.g., Ubuntu 20.04
  config.vm.box = "ubuntu/bionic64"

  # Forward port 80 from the VM to the host
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Install Docker and Docker Compose on the VM
  config.vm.provision "docker"

  # Build and run the Docker container
  config.vm.provision "docker" do |docker|
    docker.build_image "/vagrant", args: "-t my-static-website"
    docker.run "my-static-website", args: "--name my-website -d -p 80:80"
  end
end
```

Make sure you have Vagrant and VirtualBox (or another provider of your choice) installed on your system.

5. Now, you can start the VM and deploy your Docker container using Vagrant:

```bash
vagrant up
```

This will create the VM, provision it with Docker, build the Docker image from your Dockerfile, and run the container.

Your static website should now be accessible in your web browser at http://localhost:8080.

Remember to customize the base box, port mappings, and other settings in the Vagrantfile to suit your specific needs.