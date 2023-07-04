## Multiple Remote Repository Demo

### To see current remote repository

```bash
git remote -v
```

### To add a new remote repository

```bash
git remote set-url origin --add <remote_url>
```

### Change config to pull from both remote repos

Change `YOUR_PROJECT/.git/config` file like this:

```
[remote "origin"]
  fetch = +refs/heads/*:refs/remotes/origin/*
  url = git@github.com:YOUR_USERNAME/YOUR_PROJECT.git
  url = git@bitbucket.org:YOUR_USERNAME/your_project.git
  url = git@gitlab.org:YOUR_USERNAME/your_project.git

[remote "github"]
  url = git@github.com:YOUR_USERNAME/YOUR_PROJECT.git
  fetch = +refs/heads/*:refs/remotes/github/*
[remote "bitbucket"]
  url = git@bitbucket.org:YOUR_USERNAME/your_project.git
  fetch = +refs/heads/*:refs/remotes/bitbucket/*
[remote "gitlab"]
  url = git@gitlab.org:YOUR_USERNAME/your_project.git
  fetch = +refs/heads/*:refs/remotes/gitlab/*
```
