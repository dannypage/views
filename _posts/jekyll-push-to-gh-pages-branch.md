---
layout:	post
title:	"Pushing your Custom Jekyll build to GH-Pages"
date:	2020-02-08
---

I spent an hour or two trying to find a good script on how to push custom Jekyll builds to Github Pages. Surprisingly, they don't allow you to target a specific folder for the build and keep just one branch. (Outside of /docs, but I couldn't find a way to build Jekyll in /docs) - There was some complicated ways to setup Github Actions or other one-off solutions to build to a new branch. However, I finally found a solution that works for me, and I've compiled it here for my own reference and maybe it'll help you!

# Setup

`site` is your build folder.
`gh-pages` can be any other branch if you have a different name or need.

```shell
$ rm -rf _site
$ echo "_site/" >> .gitignore
$ git worktree add dist gh-pages
```

# Script

Create a new file called  `push-to-gh-pages.sh`.

```bash
jekyll build  # This can be whatever your build command is
cd _site
git add --all
git commit -m "Build at `date +'%Y-%m-%d %H:%M:%S'`"
git push origin gh-pages --force
cd ..
```

Give it Execute permission: 

`$ chmod +x push-to-gh-pages.sh`

# Putting it all together

Once you have all that set up, you can make any changes you need in your repo, then after completing your work, you can make `./push-to-gh-pages.sh` part of your deploy process and see changes on your *.github.io site!

# Citations

[Gist with a ton of info](https://gist.github.com/cobyism/4730490#gistcomment-2375522) 

[Stack Overflow with my specific need](https://stackoverflow.com/questions/33172857/how-do-i-force-a-subtree-push-to-overwrite-remote-changes)

[More on Git Worktree](https://musteresel.github.io/posts/2018/01/git-worktree-for-deploying.html)
