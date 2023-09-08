# How to install jenkins on Linux (Ubuntu)

```bash
sudo apt update
sudo apt install openjdk-17-jre
java -version
```
```bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
..........................
Start Jenkins

You can enable the Jenkins service to start at boot with the command:
```sh
sudo systemctl enable jenkins
```
You can start the Jenkins service with the command:
```sh
sudo systemctl start jenkins
```
You can check the status of the Jenkins service using the command:
```sh
sudo systemctl status jenkins
```
print the password at console
```sh
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Reference:
https://www.jenkins.io/doc/book/installing/linux/

# Jenkins Installation on AWS

## Prerequisites

Before starting the Jenkins installation, ensure you have the following prerequisites:

1. An AWS account with sufficient permissions to create and manage EC2 instances.
2. An SSH key pair for secure access to your EC2 instance.
3. Familiarity with AWS services, EC2 instances, and SSH.

## Step 1: Launch an EC2 Instance

1. Log in to your AWS Management Console.
2. Navigate to the EC2 service.
3. Click on the "Launch Instance" button.
4. Choose an Amazon Machine Image (AMI), such as Amazon Linux 2.
5. Select an appropriate instance type.
6. Configure instance details, including network settings and IAM roles.
7. Adjust storage as needed.
8. Configure security groups to allow incoming SSH (port 22) and HTTP (port 80) traffic.
9. Review your settings and launch the EC2 instance, selecting your SSH key pair.

## Step 2: Connect to Your EC2 Instance

1. Open a terminal on your local machine.
2. Connect to your EC2 instance via SSH using the following command:

   ```bash
   ssh -i /path/to/your/key.pem ec2-user@your-instance-ip

## Step 3: Install Jenkins

1. Update the package manager to ensure you have the latest package information:
 ```bash
  sudo yum update -y
```
2. Install Java, as Jenkins requires it:
```bash
  sudo yum install java-17-openjdk
```
3. Add the Jenkins repository and install Jenkins:
```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo yum install jenkins -y
```

Start Jenkins

You can enable the Jenkins service to start at boot with the command:
```sh
sudo systemctl enable jenkins
```
You can start the Jenkins service with the command:
```sh
sudo systemctl start jenkins
```
You can check the status of the Jenkins service using the command:
```sh
sudo systemctl status jenkins
```
print the password at console
```sh
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```


