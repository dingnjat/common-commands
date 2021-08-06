#Install GitLab on Linux Centos 8
### 1.Install the necessary dependencies
`sudo dnf install -y curl policycoreutils openssh-server perl`
### 2. Configure HTTP, HTTPS, SSH
Enable OpenSSH
```
sudo systemctl enable sshd
sudo systemctl start sshd
```
Open HTTP, HTTPS
```
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=https
sudo systemctl reload firewalld
```
### 3. Install Postfix to send notification emails
```
sudo dnf install postfix
sudo systemctl enable postfix
sudo systemctl start postfix
```
(not complete this part yet)
### 4. Add repository and install GitLab package
* Add repo:
EE version
`curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.rpm.sh | sudo bash`
CE version
`curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash`
* Install
EE version
`sudo dnf install -y gitlab-ee`
CE version
`sudo dnf install -y gitlab-ce`
### 5. Configure GitLab
Go to **/etc/gitlab/gitlab.rb**. Create it if not exists
Set `EXTERNAL_URL 'https://yourdomain'`
Set `gitlab_rails['initial_root_password'] = '<my_strong_password>'`
### 6. Run configuration
`sudo gitlab-ctl reconfigure`
