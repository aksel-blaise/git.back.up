Backing up Git repositories to a flash or external hard drive
================
Robert Z. Selden, Jr.
6/24/2021

## Git + remote

While GitHub is great, sometimes I just want to have redundant copies of
data on a flash drive, external hard drive, or server. This is
particularly true when I am working on large data recovery efforts while
traveling.

This is also useful for students working in my lab, when they would like
to work from home, but back up their work to the remote repository on
the university’s server.

*This workflow assumes that you are creating a new remote to backup a
Git repository that is currently on your computer.*

## Initialize a bare repository

While different approaches may work just as well, I have found that this
standardized approach ensures that I and my students can achieve the
same results.

## Navigate to Git repository and create remote

-   Write down or copy the address of the remote (i.e.,
    D:/my-git-remote)
-   Begin by navigating to the Git repository on your computer (i.e.,
    \~Desktop/my-git-repo)

``` bash
## initialise bare repo

## right click and open Git bash
git init --bare D:/my-git-remote
```

## Return to Git repository

Return to your repository, add the remote, and push.

``` bash2
## add the remote from your Git repository

git remote add my-git-remote D:/my-git-remote
git checkout master
git push my-git-remote master
```

## Sync

Congratulations! At this point, the master branch is in sync with your
remote, and I encourage you to backup your repository (at least) daily
as you work on projects in my lab.

## Troubleshooting

In the event that you plug your flash or external hard drive in and that
shows up as a different drive letter, use set-url to reassign.

``` bash3
## reassign drive letter (if needed)

git remote set-url my-git-remote E:/my-git-remote
```
