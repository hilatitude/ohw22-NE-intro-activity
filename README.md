# ohw22-NE-intro-activity
A quick introduction to git for the US NE Satellite.

Credit: Heavily borrowed from Alex Kerney's [OHW21 exercise](https://github.com/oceanhackweek/ohw21-intro-activity).

## Resources

-   [Git](https://oceanhackweek.github.io/resources/prep/git.html)
-   [GitHub](https://oceanhackweek.github.io/resources/prep/github.html)
-   [JupyterHub](https://oceanhackweek.github.io/resources/prep/jupyterhub.html)

## Create an issue

-   Create an issue 'Introduce YOUR NAME'. In that issue add a checklist of tasks to complete. You can copy the example below:

```plain
- [x] Create an issue of tasks to introduce myself
- [x] Fork repo
- [x] Clone repo to JupyterHub
- [x] Add an introduction file for yourself
- [x] Push to your fork
- [x] Make a pull request
- [ ] Review someone else's pull request (and say hello!)
- [ ] Merge your pull request after it's been reviewed
- [ ] Add an upstream remote
- [ ] Pull upstream changes into your fork
- [ ] Close this issue
```

## Fork the repo

Git is a distributed version control system, so instead of everyone working on the same repo, we fork the repository into our own GitHub account. 
This is the first step of making sure that we don't cause unintentional conflicts with changes that other people are making.

## Clone fork to JupyterHub

In your fork, you'll see a green **Code** button. Click that and it will give you a link that you can copy to clone the repository.

Then on the JupyterHub, launch a terminal and run `git clone GITHUB FORK LINK`. You'll see some output similar to:

```zsh
➜ git clone https://github.com/YOUR_USER/ohw22-NE-intro-activity.git
Cloning into 'ohw22-NE-intro-activity'...
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (5/5), done.
```

When that finishes, you'll have a new folder named `ohw22-NE-intro-activity`.

Let's change to that directory with `cd ohw22-NE-intro-activity`.

We can check the remote connections of our repository `git remote -v`. You'll see something like the following: 

```zsh
➜ git remote -v
origin  https://github.com/YOUR_USER/ohw22-NE-intro-activity.git (fetch)
origin  https://github.com/YOUR_USER/ohw22-NE-intro-activity.git (push)
```

We need to add a new remote to connect our repo with the oceanhackweek one:

```zsh
git remote add upstream https://github.com/oceanhackweek/ohw22-NE-intro-activity.git
```

## Create your introduction

Within the folder, create a markdown file with your github handle as it's name. For instance, mine would be `cathmmitchell.md`.

Within that file, write a quick introduction about yourself, maybe your name, where you're from, what institution/organization you are a part of, and how about your favorite flavor of ice cream (or if you don't like ice cream, how about favorite dessert).

## Commit your introduction

Now we need to commit your introduction.

When you're working on code, you may be making changes to many different files at once.
If you choose a single point in time, then not all files may have the right changes to work appropriately with each other.

Git takes care of this with commits, which you can think of as multiple file saves, where you can also choose exactly which files (or even which lines get included).
Adding a file to a commit is called staging it.

If you run `git status` it will now tell you that there are some changes.

```zsh
➜ git status
On branch YOUR_BRANCH_NAME
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	added:   YOUR_GITHUB_HANDLE.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Now we can run `git add YOUR_GITHUB_HANDLE.md` to stage your introduction.

And if we run `git status` again:

```zsh
➜ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	added:   YOUR_GITHUB_HANDLE.md
```

Now we can see that git understands that we want to include our introduction file in our next commit.

Then to make the commit itself, write \`git commit -m "YOUR SUMMARY OF THE CONTENTS OF THE COMMIT HERE

MORE DETAILS CAN FOLLOW ON FURTHER LINES WITHIN THE QUOTES"

One nice thing about GitHub is that you can [reference an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword) by number in a commit message, such as 'Closes #42' or 'Works on #42' which will connect the commit and the later pull request to the issue (and the issue back to them).

## Push to your fork

Now to share our awesome introduction, we need to push our commit back up to our fork.

Usually once a branch is established on GitHub, we can push to it with `git push`, but because the branch doesn't exist yet, we need to let git know what remote branch we want it to be.

For that we use `git push origin main`.

At this point git will also get cranky because of authentication.
Instead of including all those details here, [here is a link to GitHub's auth info](https://docs.github.com/en/get-started/quickstart/set-up-git).

## Make a Pull Request

Now if you go to your fork on GitHub, you should see something that says "This branch is 1 commit ahead of oceanhackweek:main". Click on the "1 commit ahead" link.

Select the Create pull request button.

You'll see that GitHub has helpfully taken the contents of your commit message and used it to fill in the pull request message.
Add any details that you may want to let any reviewers know about, and create the pull request.

## Review a Pull Request

Now that you've created a pull request of your own, lets go and review someone else's PR.

Go to the PR tab, and find another PR.

Click on the Files Changed tab and you can see the introduction that someone else made.

If you select a line, you can make a comment just about that line (or group of lines), otherwise click Review, and say hello and welcome!

Notice when you are writing a review, you can either Approve, Request Changes, or Comment, which are used to let folks know if you think their PR is ready to be merged.

We should Approve each others PRs.

## Merge PR

Once you've gotten a review and fancy green Approval checkmark on your PR, feel free to merge it!

## Get upstream changes

Now lets get other peoples introductions into our fork.

If we go back to our fork, we should see a ['Fetch upstream' button](https://github.blog/changelog/2021-05-06-sync-an-out-of-date-branch-of-a-fork-from-the-web/), which will bring our fork back into sync.

## Switch to `main`

Now that our fork is back in sync, let's get those changes locally.

Let's go back to our terminal and JupyterHub. Notice that you haven't seen other peoples intros show up, to see those you will need to `git pull` to pull the changes from `main` on your fork locally.

Now you should have other people's introductions!
