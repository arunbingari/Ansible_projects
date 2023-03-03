### Ansible Node.js Deployment Project

This project is an Ansible playbook that automates the deployment of a Node.js application on an EC2 instance. The playbook performs the following tasks:

1. Installs Node.js and NPM on the server
2. Creates a new Linux user
3. Deploys the Node.js application

### Prerequisites

Before running the playbook, make sure you have the following prerequisites:

1. An AWS EC2 instance running Ubuntu
2. Ansible installed on your local machine
3. An SSH key pair to connect to the EC2 instance

### Usage

To use this playbook, follow these steps:

1. Clone the repository to your local machine
2. Navigate to the project directory
3. Update the `hosts` file with the IP address of your EC2 instance, and the path to your SSH private key and the username for the connection
4. Update the `deploy.yml` file with the necessary configurations for your application, such as the path to your Node.js file and the name of your Linux user.

### Run the playbook using the following command:
    ansible-playbook -i hosts deploy.yml

### Playbook Overview

The `deploy.yml` playbook consists of three plays:

1. Install Node.js and NPM

The first play installs Node.js and NPM on the server by using the `apt` module. It updates the APT repository and cache, and then installs the `nodejs` and `npm` packages.

2. Create a new Linux user

The second play creates a new Linux user on the server. It uses the `user` module to create a new user with the specified name, comment, and group.

3. Deploy the Node.js application

The third play deploys the Node.js application. It first unpacks the Node.js file and installs the application dependencies using the `unarchive` and `npm` modules, respectively. Then, it starts the application using the `command` module and registers the output to a variable. Finally, it uses the `debug` module to print the output to the console.
