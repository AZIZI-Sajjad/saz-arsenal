# saz-linux

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/linux

## Linux - git - Install git Debian/Ubuntu
```
sudo apt update ; apt install git
```

## Linux - git - Install git RHEL/CentOS/Amazon-Linux
```
sudo yum update ; yum install git
```


## Linux - git - Connect to git with SSH - step 1/4 - Add UserbName
```
ssh-keygen -t ed25519 -C "New-Git-Key"
cat ~/.ssh/id_git
cat ~/.ssh/id_git.pub
  Copy the Public SSH-KEY contect into git account on the Git
nano ~/.ssh/config
ssh -T git@<git_url_without_https_exemple-github.com>
```


## Linux - git - Connect to git with SSH - step 2/4 - Add E-Mail Address
```
git config --global user.email <UserName>
```


## Linux - git - Connect to git with SSH - step 3/4 - Add E-Mail Address
```
git config --global user.email <@Mail>
```


## Linux - git - Connect to git with SSH - step 4/4 - Check Connectivity
```
ssh -T git@<git_url_without_https_exemple-github.com>
```


## Linux - git - Replace remote URL 
```
git remote set-url origin git@<Link_to_project_copied_with_.git>
```


## Linux - git - Add User with HTTPS
```
mkdir test-git-https/
cd test-git-https/
git config --global user.name <UserName>
git config --global user.email <@Mail>
git init
git clone --branch=master <https_link_to_ptoject>
cd protect_name/
nano -c README.md
git status
git diff
git add .
git commit -m "[TEST_ACCESS_README.md]"
git push
git status
```


