#  Docker Static Web Stack

This repository contains configurations and files to set up a virtual machine, Vagrant, Docker, and serve a static website.

## Prerequisites

1. [VirtualBox](https://www.virtualbox.org/)
2. [Vagrant](https://www.vagrantup.com/)
3. [Docker](https://www.docker.com/get-started)

## Getting Started

### Virtual Machine

1. Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
2. Create a new virtual machine or use the provided `.ova` file to import a VM.

### Vagrant

1. Clone this repository: `git clone [repo-url]`.
2. Navigate to the repository directory: `cd [repo-name]`.
3. Run `vagrant up` to initialize and provision the virtual machine.
4. SSH into the VM using `vagrant ssh`.

### Docker

Inside the virtual machine or on your host:

1. Build the Docker image: `docker build -t my-static-site:latest .`
2. Run the Docker container: `docker run -p 8080:80 my-static-site:latest`.

### Accessing the Static Website

Once the Docker container is running, access the static website by navigating to `http://localhost:8080` in your browser.

## Structure

- `/vm`: Contains virtual machine configuration and related files.
- `/vagrant`: Contains Vagrantfile and provisioning scripts.
- `/docker`: Contains Dockerfile and other Docker-related configurations.
- `/static-website`: Contains the static website's HTML, CSS, JS, and other assets.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.