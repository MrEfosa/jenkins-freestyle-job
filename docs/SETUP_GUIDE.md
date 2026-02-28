# Setup Guide for Jenkins Freestyle Job on DigitalOcean

This guide provides step-by-step instructions for setting up Jenkins with Docker on DigitalOcean droplets.

## 1. Setting up DigitalOcean Droplets

### Creating a New Droplet
1. Log in to your DigitalOcean account.
2. Navigate to the "Droplets" section and click on the "Create Droplet" button.
3. Select `Ubuntu` as your operating system.

### Choosing an Image and Plan
- Select the latest version of Ubuntu.
- Choose a plan based on your resource needs (e.g., Standard Plan). 
- Select the default data center region.

### Configuring SSH Keys
1. If you have SSH keys set up, select your SSH key. 
2. If not, click on "New SSH Key" and follow the instructions to create one. 
3. Complete the droplet creation.

## 2. Installing Docker

### Installing Docker on Ubuntu
1. Connect to your droplet via SSH:
   ```bash
   ssh root@your_droplet_ip
   ```
2. Update your package repository:
   ```bash
   apt-get update
   ```
3. Install Docker:
   ```bash
   apt-get install -y docker.io
   ```
4. Start Docker and enable it on boot:
   ```bash
   systemctl start docker
   systemctl enable docker
   ```

### Verifying Docker Installation
- Run the following command to verify that Docker is installed:
  ```bash
  docker --version
  ```

## 3. Deploying Jenkins

### Running Jenkins in a Docker Container
1. Pull the Jenkins image:
   ```bash
   docker pull jenkins/jenkins:lts
   ```
2. Run the Jenkins container:
   ```bash
   docker run -d -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts
   ```

### Configuring Jenkins
- Access Jenkins by navigating to `http://your_droplet_ip:8080` in your web browser. 
- Follow the on-screen instructions to unlock Jenkins using the initial admin password found in the container:
  ```bash
  docker exec -it <container_id> cat /var/jenkins_home/secrets/initialAdminPassword
  ```

## 4. Configuring a Freestyle Job

### Creating a New Job in Jenkins
1. Click on "New Item" in the Jenkins dashboard.
2. Name your job and select "Freestyle project."
3. Click "OK" to proceed.

### Adding Build Steps
- In the job configuration, scroll down to the "Build" section.
- Add your desired build steps and save the job.

---

By following these steps, you will have Jenkins up and running on a DigitalOcean droplet, allowing you to configure freestyle jobs efficiently.