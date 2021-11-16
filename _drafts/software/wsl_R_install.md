OS: windows 10 Pro Version 1909 (OS build 18363.1256)
WSL2: ubuntu 20.04

r-base on Ubuntu for windows installs R 3.6.3 (as of 2020-02-09)

R information for installing on Ubuntu is available here:
https://cran.r-project.org/bin/linux/ubuntu/fullREADME.html

At the link above, under Secure Apt are options for how to add the key. The Mischan Toosarani approach worked for me

```
gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
gpg -a --export E298A3A825C0D65DFD57CBB651716619E084DAB9 | sudo apt-key add -
```

Add relevant GPG key

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
