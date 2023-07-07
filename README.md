## Push and Pull from multiple remote Git Repositories Demo

### To see the current remote repository

```bash
git remote -v
```

### To add a new remote repository

```bash
git remote set-url origin --add <remote_url>
```

### To pull from a remote repository

Change `YOUR_PROJECT/.git/config` file like this:

From this:

```bash
[remote "origin"]
  fetch = +refs/heads/*:refs/remotes/origin/*
  url = git@github.com:YOUR_USERNAME/YOUR_PROJECT.git ## git pull command will pull from this repo from GitHub
  url = git@gitlab.com:YOUR_USERNAME/YOUR_PROJECT.git
  url = git@bitbucket.org:YOUR_USERNAME/YOUR_PROJECT.git
```

To this:

```bash
[remote "origin"]
  fetch = +refs/heads/*:refs/remotes/origin/*
  url = git@gitlab.com:YOUR_USERNAME/YOUR_PROJECT.git  ## git pull command will pull from this repo from gitlab
  url = git@github.com:YOUR_USERNAME/YOUR_PROJECT.git
  url = git@bitbucket.org:YOUR_USERNAME/YOUR_PROJECT.git
```

### Change config to pull from both remote repos

Change `YOUR_PROJECT/.git/config` file like this:

```
[remote "origin"]
  fetch = +refs/heads/*:refs/remotes/origin/*
  url = git@github.com:YOUR_USERNAME/YOUR_PROJECT.git
  url = git@bitbucket.org:YOUR_USERNAME/YOUR_PROJECT.git
  url = git@gitlab.com:YOUR_USERNAME/YOUR_PROJECT.git

[remote "github"]
  url = git@github.com:YOUR_USERNAME/YOUR_PROJECT.git
  fetch = +refs/heads/*:refs/remotes/github/*
[remote "bitbucket"]
  url = git@bitbucket.org:YOUR_USERNAME/YOUR_PROJECT.git
  fetch = +refs/heads/*:refs/remotes/bitbucket/*
[remote "gitlab"]
  url = git@gitlab.com:YOUR_USERNAME/YOUR_PROJECT.git
  fetch = +refs/heads/*:refs/remotes/gitlab/*
```

### To pull from both repos

```bash
## Pull from GitHub
git pull github master

## Pull from GitLab
git pull gitlab master

## Pull from BitBucket
git pull bitbucket master
```
