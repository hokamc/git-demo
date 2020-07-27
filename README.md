<p align="center">
  <a href="" rel="noopener">
 <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Git-logo.svg/1024px-Git-logo.svg.png"  width="200" alt="Git"></a>
</p>
<h2 align="center">Git Demo</h2>

<div align="center">

[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)]()
[![Status](https://img.shields.io/badge/status-active-success.svg)]()

</div>

---

<p align="center"> Share some useful Git tricks
    <br> 
</p>

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Multiple ssh keys](#multiple-ssh-keys)
- [Multiple name and email](#multiple-name-and-email)
- [Authors](#authors)

## Multiple ssh keys

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

## Multiple name and email

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



## Authors

- [@hokamc](https://github.com/hokamc)

