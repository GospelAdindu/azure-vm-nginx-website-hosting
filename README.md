## Project Overview
This project demonstrates how to deploy and host a simple static website on a Linux Virtual Machine in the cloud. The objective of the project is to understand how cloud infrastructure works by creating a virtual server, configuring networking, installing a web server, and making the website accessible through a public IP address.

The project focuses on hands-on cloud fundamentals such as Virtual Machines, networking configuration, Linux server setup, and web server deployment.

## Cloud Platform
Microsoft Azure

## Services Used
- Azure Virtual Machine
- Virtual Network (VNet)
- Network Security Group (NSG)
- Public IP Address
- Linux (Ubuntu)
- Nginx Web Server

## Architecture Overview
User → Internet → Public IP Address → Azure Virtual Machine → Nginx Web Server → Static Website

The user accesses the website through the internet using the public IP address assigned to the virtual machine. The request reaches the Azure Virtual Machine where the Nginx web server is installed and configured to serve the static website files.

## Deployment Steps

### 1. Create a Virtual Machine
A Linux Virtual Machine (Ubuntu) was created in Azure. During the setup process, the necessary configurations such as region, authentication method, and instance size were selected.

### 2. Configure Networking
A Virtual Network and Network Security Group were configured to allow inbound traffic. Port **80 (HTTP)** was opened to allow web traffic to reach the server.

### 3. Connect to the Virtual Machine
The virtual machine was accessed remotely using SSH from the terminal.

Example:
```
ssh username@public-ip-address
```

### 4. Install the Web Server
Nginx was installed on the Linux server to host the website.

Commands used:
```
sudo apt update
sudo apt install nginx -y
```

### 5. Start and Enable Nginx
The Nginx service was started and enabled to run automatically.

```
sudo systemctl start nginx
sudo systemctl enable nginx
```

### 6. Deploy the Website Files
The static website files (HTML, CSS, or simple index page) were placed inside the default Nginx web directory:

```
/var/www/html
```

### 7. Test Website Access
The public IP address of the Azure Virtual Machine was opened in a web browser to confirm that the website was successfully deployed and accessible from the internet.
