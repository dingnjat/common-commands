# Install GitLab on Linux Centos 8
### 1. Install the necessary dependencies
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
(not complete this part yet, but still can skip this step)
```
sudo dnf install postfix
sudo systemctl enable postfix
sudo systemctl start postfix
```
### 4. Add repository and install GitLab package
* Add repo: <br>
EE version <br>
`curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.rpm.sh | sudo bash` <br>
CE version <br>
`curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash` <br>
* Install <br>
EE version <br>
`sudo dnf install -y gitlab-ee` <br>
CE version <br>
`sudo dnf install -y gitlab-ce` <br>
### 5. Configure GitLab
Go to **/etc/gitlab/gitlab.rb**. Create it if not exists <br>
Set `EXTERNAL_URL 'https://yourdomain'` <br>
Set `gitlab_rails['initial_root_password'] = '<my_strong_password>'` <br>
### 6. Run configuration
`sudo gitlab-ctl reconfigure`
