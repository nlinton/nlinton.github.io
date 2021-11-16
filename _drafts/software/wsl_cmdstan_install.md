Best to follow the cmdstan guide

https://mc-stan.org/docs/2_26/cmdstan-guide/cmdstan-installation.html

```
git clone https://github.com/stan-dev/cmdstan.git --recursive
cd cmdstan
make build
```

Then it automatically saves to `/home/USERNAME/cmdstan/stan/lib/stan_math` if another folder (i.e. on /mnt) is not specified

---

Alternatively, download cmdstan tar.gz from github
Save to desired location
Extract from tar.gz
```
tar -xf cmdstan-2.??.?.tar.gz
```
Add local make vars if needed (local file in make folder with necessary specs)
```
make build
```
