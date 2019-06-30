---
layout: post
title:      "Shape CLI Git Commands"
date:       2019-06-30 23:44:57 +0000
permalink:  shape_cli_git_commands
---

Setting up Git, Clone Repo and edit README

Find the project README [here](https://jessekathryn.github.io/shapecli_readme).

1. Go to the sandbox [here](https://learn.co/tracks/full-stack-web-development-v7/git-and-github/git/introduction-to-version-control)

2. Open Sandbox and type in your new gem name

```
bundle gem 'name_of_gem'
```

3. Answer questions according to the settings for your app

4. CD into your new app's directory

5. Go to Github and create a new repository

6. Commit and push to repo from sandbox

```
git add .
```
```
git commit -m  "first commit"
```
```
git remote add origin <github.url>
```
```
git push -u origin master
```

7. Refresh browser and delete folders leftover from sandbox learn.co

8. Copy Repo at (in this case) git@github.com:jessekathryn/shape_cli.git or SSH and return to Sandbox

9. Clone Repo

```
git clone git@github.com:jessekathryn/shape_cli.git
```

10. CD into folder and then make a change to the README, such as a description, and then commit change by first staging it

```
git add .
```

11. Now commit with a message tag

```
git commit -m "Readme update"
```

12. Push your code to your repo and you're ready to continue making changes

Below is a sample console for your static reference 

```
[23:22:31] (master) Development

// ♥ git clone git@github.com:jessekathryn/shape_cli.git

Cloning into 'shape_cli'...
remote: Enumerating objects: 20, done.
remote: Counting objects: 100% (20/20), done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 20 (delta 2), reused 20 (delta 2), pack-reused 0
Receiving objects: 100% (20/20), 5.45 KiB | 0 bytes/s, done.
Resolving deltas: 100% (2/2), done.
Checking connectivity... done.
[23:26:19] (master) Development

// ♥ git add .

[23:30:43] (master) Development

// ♥ git commit -m "readme update"

[master e8763fa] readme update
 2 files changed, 1 insertion(+), 11 deletions(-)
 delete mode 100644 README.md
 create mode 160000 shape_cli
[23:30:56] (master) Development

// ♥ git push

Counting objects: 2, done.
Writing objects: 100% (2/2), 240 bytes | 0 bytes/s, done.
Total 2 (delta 0), reused 0 (delta 0)
To git@github.com:jessekathryn/learn-co-sandbox.git
   c6cb5db..e8763fa  master -> master
```
