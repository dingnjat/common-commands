# Install Jenkins
## Prerequisite
Java 8 or Java 11
## Install on CentOS 8
### Add Jenkins Software Repository
Run: <br>
`sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo` <br>
If not download correctly, we need to add manually: <br>
1. Create and open repo file: `sudo nano /etc/yum.repos.d/jenkins.repo` <br>
2. Enter the following lines and save:
```
[jenkins]
name=Jenkins-stable
baseurl=http://pkg.jenkins.io/redhat
gpgcheck=1
```
3. Import the GPG key to ensure your software is legitimate <br>
`sudo rpm --import https://pkg.jenkins.io/redhat/jenkins.io.key`
### Install Jenkins package
Run: `sudo dnf install jenkins`
### Start Jenkins service
Enable: `sudo systemctl enable jenkins` <br>
Start: `sudo systemctl start jenkins` <br>
Restart: `sudo systemctl restart jenkins` <br>
### Change port
Change the port in file `/etc/sysconfig/jenkins` and restart service <br>
You might have to change port in `/usr/lib/systemd/system/jenkins.service`
### Run and Setup
Open the URL and follow the instructions of Jenkins
## Install on Ubuntu 22.04
### Add Jenkins Software Repository
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key |sudo gpg --dearmor -o /usr/share/keyrings/jenkins.gpg
sudo sh -c 'echo deb [signed-by=/usr/share/keyrings/jenkins.gpg] http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```
### Install Jenkins package
You may run update command before installing Jenkins <br>
Run: `sudo apt-get install jenkins`
### Start Jenkins service
Enable: `sudo systemctl enable jenkins` <br>
Start: `sudo systemctl start jenkins` <br>
Restart: `sudo systemctl restart jenkins` <br>
### Change port
Change the port HTTP_PORT in file `/etc/default/jenkins` and restart service <br>
You might have to change port Environment="JENKINS_PORT=8080" in `/usr/lib/systemd/system/jenkins.service`
### Run and Setup
Open the URL and follow the instructions of Jenkins
