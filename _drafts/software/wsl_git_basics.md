
Configure username and email address:
```
$ git config --global user.name "your_github_username"
$ git config --global user.email "your_github_email"
$ git config -l
```

Clone a repository:
```
$ git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
```

Save credentials:
```
$ Username for 'https://github.com' : username
$ Password for 'https://github.com' : give your personal access token here
$ git config --global credential.helper cache
```

Delete cached credentials:
```
$ git config --global --unset credential.helper
$ git config --system --unset credential.helper
```

Pull with -v to verify: `$ git pull -v`

---


Basic flow for committing:
1. `git commit -a -m 'some message'`
2. `git push -u origin main`


Putting your R package on github:
https://kbroman.org/pkg_primer/pages/github.html

Install `gitsome` for `gh` commands
`sudo apt install gitsome`

---

Remove git lock file:
In main respository folder run `rm -f .git/index.lock`
