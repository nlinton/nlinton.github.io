OS: windows 10 Pro Version 1909 (OS build 18363.1256)
WSL2: ubuntu 20.04

<!-- Try installing with no lock: `install.packages("dplyr", dependencies = TRUE, INSTALL_opts = '--no-lock')` -->

<!-- On linux, you can execute `unlink("/home/USERNAME/src/Rlibs/00LOCK-Rcpp", recursive = TRUE)` -->

## Linux

On linux, sometimes R packages may fail to install because a linux library needs to be installed. In Jupyter, the following error message `"installation of package 'curl' had non-zero exit status"` was not very informative, but trying again to install the package (curl was a dependency) provided a more informative error message
```
Configuration failed because libcurl was not found. Try installing:
 * deb: libcurl4-openssl-dev (Debian, Ubuntu, etc)
 * rpm: libcurl-devel (Fedora, CentOS, RHEL)
 * csw: libcurl_dev (Solaris)
If libcurl is already installed, check that 'pkg-config' is in your
PATH and PKG_CONFIG_PATH contains a libcurl.pc file. If pkg-config
is unavailable you can set INCLUDE_DIR and LIB_DIR manually via:
R CMD INSTALL --configure-vars='INCLUDE_DIR=... LIB_DIR=...'
```
which could be addressed using
```
sudo apt-get install libcurl4-openssl-dev
```
However, the original package `rstan` and the dependency `V8` were still not installing. Another component was missing:
```
Configuration failed to find the libv8 engine library. Try installing:
 * deb: libv8-dev or libnode-dev (Debian / Ubuntu)
 * rpm: v8-devel (Fedora, EPEL)
 * brew: v8 (OSX)
 * csw: libv8_dev (Solaris)
Alternatively, on Linux (x86_64) or MacOS you can set environment variable:
    DOWNLOAD_STATIC_LIBV8=1
to automatically download a static version of libv8.
To use a custom libv8, set INCLUDE_DIR and LIB_DIR manually via:
R CMD INSTALL --configure-vars='INCLUDE_DIR=... LIB_DIR=...'
```
Employing sudo again:
```
sudo apt-get install libv8-dev
```

---
In another instance, trying to install devtools, xml2 was locked
```
mv: cannot move '/usr/local/lib/R/site-library/00LOCK-xml2/00new/xml2' to
'/usr/local/lib/R/site-library/xml2': Permission denied
```
One thread suggested updating all packages
```
update.packages(ask=FALSE)
```
But xml2 was still locked after doing this. Possibly the problem is related to running R in root.

Adding "no-lock" to the install command solved it
```
install.packages("xml2", dependencies=TRUE, INSTALL_opts = c('--no-lock'))
```

---
`pkgdown` also had non-zero exit status, this because it needed `freetype` installed.
```
Configuration failed to find the harfbuzz freetype2 fribidi library. Try installing:
 * deb: libharfbuzz-dev libfribidi-dev (Debian, Ubuntu, etc)
```

Using `sudo apt-get install xxx` for those packages solved it.

---

**Devtools on Ubuntu**
<!-- https://www.digitalocean.com/community/tutorials/how-to-install-r-packages-using-devtools-on-ubuntu-18-04 -->

First, we need to ensure that the necessary system dependences are installed.

`$ sudo apt install build-essential libcurl4-gnutls-dev libxml2-dev libssl-dev`

Then, it might be least problematic to install devtools from within Ubuntu rather than Jupyter/RStudio, so enter R's shell as root:

`$ sudo -i R`

From there, install devtools

`install.packages('devtools')`


Source: https://www.digitalocean.com/community/tutorials/how-to-install-r-packages-using-devtools-on-ubuntu-18-04

---

Package magick also needed to be installed first in Ubuntu.

```
sudo apt-get install libmagick++-dev
```
