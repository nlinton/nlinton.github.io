Best to follow the cmdstan guide

https://mc-stan.org/docs/2_26/cmdstan-guide/cmdstan-installation.html

Installing a new cmdstan

Navigate to parent folder (using WSL this would be on /mnt/c/ or /mnt/d/)

`git clone https://github.com/stan-dev/cmdstan.git NEWFOLDERNAME --recursive`

Add local make file.

```
cd NEWFOLDERNAME
make build
```


---

Better yet, let's use RStudio server.
