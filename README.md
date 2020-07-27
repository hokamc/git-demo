<p align="center">
  <a href="" rel="noopener">
 <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Git-logo.svg/1024px-Git-logo.svg.png"  width="200" alt="Git"></a>
</p>
<h1 align="center">Git Demo</h1>

<div align="center">

[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)]()
[![Status](https://img.shields.io/badge/status-active-success.svg)]()

</div>

<p align="center"> Share some useful Git tricks
    <br> 
</p>

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Multiple ssh keys for different accounts](#multiple-ssh-keys-for-different-accounts)
- [Multiple name and email for different repositories](#multiple-name-and-email-for-different-repositories)
- [Remove sensitive file from repository](#remove-sensitive-file-from-repository)
- [Authors](#authors)

## Multiple ssh keys for different accounts

generate ssh key
```bash
$ ssh-keygen -t rsa
```
list all ssh keys
```bash
$ ls ~/.ssh/
```
create a ssh config
```bash
$ touch ~/.ssh/config
```
add each ssh to config
```
#yyyy account
Host xxxx.github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_xxxx
```
git clone according to new Host
```bash
$ git clone git@xxxx.github.com:yyyy/zzzz.git
```

## Multiple name and email for different repositories

create a gitconfig
```bash
$ touch ~/.xxxx.gitconfig
```
add to .xxxx.gitconfig
```
[user]
  email = youremail
  name = yourname
```
update global config ~/.gitconfig
```
[user]
  name = John Doe
  email = john@doe.tld

[includeIf "gitdir:TARGET_FOLDER_PATH"]
  path = ~/.xxxx.gitconfig
```
> all repositories under TARGET_FOLDER_PATH would use .xxxx.gitconfig


## Remove sensitive file from repository

remove file from repository
```bash
$ git filter-branch -f --tree-filter "rm -f PATH_OF_FILE"
```

clear temporary history
```bash
$ rm -rf .git/refs/original/refs/
```

expire all old history
```bash
$ git reflog expire --all --expire=now
```

remove unreachable objects
```bash
$ git gc --prune=now
```

push again
```bash
$ git push -f
```


## Authors

- [@hokamc](https://github.com/hokamc)

