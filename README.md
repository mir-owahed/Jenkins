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


