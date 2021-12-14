## Basic R
OS: windows 10 Pro Version 1909 (OS build 18363.1256)
WSL2: ubuntu 20.04

Installing R using r-base on WSL seems to install a version other than the latest version.

R information for installing on Ubuntu is available here:
https://cran.r-project.org/bin/linux/ubuntu/fullREADME.html

At the link above, under Secure Apt are options for how to add the key. The Mischan Toosarani approach worked for me

First, add relevant GPG key
```
gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
gpg -a --export E298A3A825C0D65DFD57CBB651716619E084DAB9 | sudo apt-key add -
```

Then, add repository, checking which distribution to use with `lsb_release -a` if unknown.
```
sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/'
```

Alternatives to focal are `bionic`, `groovy`, and `xenial`

Install R using added respository (cran40 -> R4.0)
```
sudo apt install r-base
```

Run R as sudo to start as root
```
sudo -i R
```

---
## What about Rstudio server?

OS: windows 10 Pro Version 20H (OS build 19042.1288)
WSL2: Ubuntu 20.04

For RStudio in session - type `quit("yes")` and it will end the session and pop up a button asking if you want a new session.

`sudo rstudio-server start` and enter password for WSL.

Once it is started you navigate to http://localhost:8787/

Username and password are same as for WSL.
