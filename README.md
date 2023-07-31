# install-jenkins
How to install jenkins on Linux (Ubuntu)

sudo apt update

sudo apt install openjdk-17-jre

java -version

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

..........................
Start Jenkins

You can enable the Jenkins service to start at boot with the command:

sudo systemctl enable jenkins

You can start the Jenkins service with the command:

sudo systemctl start jenkins

You can check the status of the Jenkins service using the command:

sudo systemctl status jenkins

The command: sudo cat /var/lib/jenkins/secrets/initialAdminPassword will print the password at console.


Reference:
https://www.jenkins.io/doc/book/installing/linux/


