# GitHub Basics

## What is version control?

## What is distributed version control?

## What is GitHub?

GitHub is a hosting service for git repositories. It is also has many other features that make life easier for programmers (release distribution, issue tracking, websites, etc). 

## What are GitHub repos?

## Cloning a repo

This will copy a repository down to your local machine. From here, you can mess with the code all you want, and the copy on GitHub will be unaffected.

https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository

## Forking a repo

There is a good chance that you will not have permission to make changes to another person's repository. The GitHub way of resolving this is by allowing you to make a copy of a repository, make your changes there, and ask the owner of the repository to copy your changes back into their repository.

https://docs.github.com/en/get-started/quickstart/fork-a-repo
https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks

## Pulling branches

If the repository has changed since you last cloned it, you can copy those new changes down to your local copy. If you made a branch, this will not even overwrite your changes.

https://docs.github.com/en/get-started/using-git/getting-changes-from-a-remote-repository


## Checking out branches


## Creating a branch

You can create branches to try out ideas without necessarily making them a permanent part of your repository. You might also create a branch to slowly accumulate features, and then release them all at once.

https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository

## Committing changes

Commiting changes keeps a snapshot of your project at a certain point in time. Each commit is like a checkpoint that you can roll back to as needed.

https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/about-commits
https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/committing-and-reviewing-changes-to-your-project

## Pushing branches

Pushing a branch sends changes that were commited on your local repository up to the repository on GitHub. This allows other users to see those changes, and pull them back down to your own repository.

https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository
https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/pushing-changes-to-github

## Merging branches

Merging a branch combines the changes from two branches into a single set of changes. You might do this after creating branches to test multiple possible ways to change a dictionary, or to consolidate the changes that multiple contributors have made.

https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request
https://docs.github.com/en/get-started/using-git/getting-changes-from-a-remote-repository#merging-changes-into-your-local-branch

## Submitting pull requests

A pull request is an invitation to the owner of a repository to incorporate the changes that you have made into their own repository. This is how you will finally get any changes that you have made into the primary repository.

https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests