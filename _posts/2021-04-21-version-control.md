---
layout: post
title: "Version control"
categories: original
author: "Conrad Maaijen"
---

All our projects use Git, all with a repository hosted on GitHub. Since we're a small team, and most projects have only two  people working on it simultaneously, we have pretty loose Git guidelines since we rarely bump into conflicts.

<!--more-->

## Repo naming conventions

If the repo contains the source code of a site its name should be the main naked domain name of that site. It should be lowercased.

Bad: https://www.maayen.nl, www.maayen.nl, Maayen.nl<br>
Good: maayen.nl

Sites that are hosted on a subdomain may use that subdomain in their name

Bad: blog.maayen<br>
Good: blog.maayen.nl

## Branches

If you're going to remember one thing from this post, remember this: Once a project has gone live, the master branch must always be stable. It should be safe to deploy the master branch to production at all times. All branches are assumed to be active; stale branches should get cleaned up accordingly.

#### PROJECTS IN INITIAL DEVELOPMENT

Projects that aren't live yet have at least two branches: main and develop. Avoid committing directly on the master branch, always commit through develop.

If you'd like to create a feature branch, make sure it's branched from develop, not main.

#### LIVE PROJECTS

There's no strict ruling on feature branch names, just make sure it's clear enough to know what they're for. Branches may only contain lowercase letters and hyphens.

Bad: feature/mailchimp, random-things, develop<br>
Good: feature-mailchimp, fix-deliverycosts or updates-june-2016

#### PULL REQUESTS

Merging branches via GitHub pull requests is a requirement.

Make sure your branch can be merged and commits can be squashed via an interface
Future you wants a quick way to retrieve that point in history by browsing passed pull requests

#### MERGING AND REBASING

Ideally, rebase your branch regularly to reduce the chance of merge conflicts.
If your push is denied, rebase your branch first using *git rebase*

## Commits

There's not strict ruling on commits in projects in initial development, however, descriptive commit messages are recommended. After a project has gone live, descriptive commit messages are required. Always use present tense in commit messages.

Non-descriptive: wip, commit, a lot, solid<br>
Descriptive: Update deps, Fix vat calculation in delivery costs<br>
Ideally, prefer granular commits.

Acceptable: Cart fixes<br>
Better: Fix add to cart button, Fix cart count on home

## Git Tips

#### MOVING COMMITS TO A NEW BRANCH

First, create your new branch, then revert the current branch, and finally checkout the new branch.

Don't do this to commits that have already been pushed without double checking with your collaborators!

```bash
git branch my-branch
git reset --hard HEAD~3 # OR git reset --hard <commit>
git checkout my-branch
```

#### SQUASHING COMMITS ALREADY PUSHED

Only execute when you are sure that no-one else pushed changes during your commits.

First, copy the SHA from the commit previous to your commits that need to be squashed.

```bash
git reset --soft <commit>
git commit -m "your new message"
git push --force
```

#### CLEANING UP LOCAL BRANCHES

After a while, you'll end up with a few stale branches in your local repository. Branches that don't exist upstream can be cleaned up with git remote prune origin. If you want to ensure you're not about to delete something important, add a *--dry-run flag*.

## Resources

* Most of this is based on the [GitHub Flow](https://guides.github.com/introduction/flow/)
* Merge vs. rebase on [Atlassian](https://www.atlassian.com/git/tutorials/merging-vs-rebasing/workflow-walkthrough)
* Merge vs. rebase by [@porteneuve](https://medium.com/@porteneuve/getting-solid-at-git-rebase-vs-merge-4fa1a48c53aa)
