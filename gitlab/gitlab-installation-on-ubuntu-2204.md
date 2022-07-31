Gitlab has not supported Ubuntu 22.04 yet (31/07/2022), so we will configure Gitlab repository for Ubuntu 20.04 on Ubuntu 22.04
1. Update <br> `sudo apt-get update`
2. Install essential packages <br> `sudo apt-get install tzdata curl ca-certificates openssh-server`
3. Add key
```
gpg_key_url="https://packages.gitlab.com/gitlab/gitlab-ce/gpgkey"
curl -fsSL $gpg_key_url| sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/gitlab.gpg
```
4. Add repo
```
sudo tee /etc/apt/sources.list.d/gitlab_gitlab-ce.list<<EOF
deb https://packages.gitlab.com/gitlab/gitlab-ce/ubuntu/ focal main
deb-src https://packages.gitlab.com/gitlab/gitlab-ce/ubuntu/ focal main
EOF
```
5. Update again <br> `sudo apt-get update`
6. Install Gitlab CE <br> `sudo apt-get install gitlab-ce`
7. Check version <br> `sudo gitlab-rake gitlab:env:info`
