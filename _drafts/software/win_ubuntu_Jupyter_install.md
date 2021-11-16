OS: windows 10 Pro Version 1909 (OS build 18363.1256)
WSL2: ubuntu 20.04
Python: 3.8.5


Start by updating everything.
```
sudo apt update -y && sudo apt upgrade -y
```

Install python3 and pip
```
sudo apt install -y python3 python3-pip
```

Now install jupyter lab
```
pip3 install jupyterlab
```

Choose directory you want to launch Jupyter lab from in Windows using `cd /mnt/c/folder/folder/folder` then
```
jupyter lab --no-browser
```


<!---
You can also make this a shortcut
```
C:\Windows\System32\wsl.exe jupyter lab --no-browser
```
--->

R may ask to make a personal library because `lib = usr/local/lib/R/site-library` is not writeable.
```
'~/R/x86_64-pc-linux-gnu-library/4.0'
```
