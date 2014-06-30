---
layout: post
title: "Why Git is superior to SVN for the modern workflow"
description:
category: blog
tags: [programming, svn, version control, git]
comments: false
image:
  background: witewall_3.png
share: true
---

Anyone who deals with legacy codebases (by legacy I mean >5 years) will most likely have to deal with using SVN for version control.

Thankfully, I started off with `git` learning the branching model of version control, and found that as I progressively learnt the more advanced features that it integrated well with my both my personal and team workflow.

Here are some reasons on why `git` is superior to `svn`:

1. **Local branching**

    Creating local branches is central to `git`'s workflow.
    This inexpensive mechanism fosters the trial of new feature branches because: 1. your commits are local, other people can't see it until you push to the remote, and 2. your intermediate commits (before you complete your branch) can be used for backtracking and even squashed to create a cleaner commit history.
    The latter point is perhaps one of the bigger advantages of using `git` over `svn`: `svn` in your typical centralised server setting does not have the concept of local branching and hence one is unable to create intermediate commits to save progress on local work. A (hacky) workaround is to create diff patches, but this obviously lacks the ability to revert and move around the intermediate commits.

2. **Lightweight branching**

    The cost of branching is extremely light on `git`, however in `svn` once a branch has been created, one typically checks it out separately to the trunk, and you end up with a very large memory footprint on your local machine (not withstanding the long download times for larger projects). 

3. **Decentralisation**

   In the `git` workflow, each person working on it clones the repository, essentially creating distributed backups of all the commit history.
   The wonderful thing about decentralisation means there is no single point of failure. 
   More often than not, there will be a networking or processing problem on the SVN server, which essentially blocks all development since commits can not longer be pushed to the centralised server.

To summarise, `git` really is the superset of `svn` in terms of features (it even has `git-svn`) and there's no real reason why `svn` should be used in the modern development workflow.
