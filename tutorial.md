# What is Git?

The description from [git-scm.com](http://git-scm.com) is as follows:

> Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

In more general terms, git is a way to keep track of changes in files. A git repository is like a folder on your computer, but one that can track the changes that you make. The folder can contain any kind of data, but to take full advantage of the change tracking, the data should be plain text. Git can track the changes in text files (e.g. csv files, scripts, html documents, json data) line by line, and point out which lines changed between versions of each file. You have to decide for yourself what constitutes a change, and document it, but git enforces and systematizes these changes, allowing you to go back to previous versions and undo a single change that you made a month ago.
 
Git allows for a variety of other ways of dealing with changing data in folders, like cloning repositories (think copying folders) and creating new versions of repositories called forks.

However, Git by itself allows this only on one machine. It's useful, but its real power is in allowing for distributed contributions to a single repository. One way to enable this is GitHub.

# What is GitHub?

More or less what it says on the tin, GitHub is a hub for Git repositories. It's a central host for these repositories, that allow people to collaborate in the open on projects. Most of its funding comes from people who don't want to work in the open, but still want to use it as a central hub for their projects, and take advantage of its many resources. Since these folks work in software engineering and industry more broadly, they've got the funds to subsidize our relatively low-impact use of the service.

GitHub comes with a lot of nifty things that it does, mostly related to displaying files in ways that make sense. It can show you a csv file as a table, or a GeoJson file as a map, or a markdown file like this one as formatted text (more on markdown later)

GitHub also allows for relatively simple websites to be created using this same infrastructure, rendering markdown files into beautiful HTML using a Ruby Gem called Jekyll. (Ruby is a programming language, Gems are self-contained extensions to Ruby that let you do more cool stuff with the language easily.) By the end of this tutorial, you should be able to create a GitHub Pages website for a project of your own, and update it with new content with ease.

# Wait, what's Markdown?

Markdown is a simple markup language for text, intended to let you write readable plain text in a standard way that various interpreters (like Jekyll) can turn into the HTML that you're used to seeing on the web. If you scroll to the top of this page and click "Raw" you'll see the Markdown version of what you're reading. Hopefully you'll still find it readable, if not as polished. You can find out more about Markdown [here](https://daringfireball.net/projects/markdown/).

# Fork this, I'm out

In the language of Git, a fork (noun) is a copied version of a repository that diverges from the original. To fork (verb) is to create such a version. Yes, all of those jokes you're thinking of have been, and will continue to be made.

Right now, you're going to fork this repository, so that you have a version of it that's all your own. Scroll up to the top of this page and click "Fork". Now you'll have a copy of this repository all to yourself. Once you've done that come back to this page. Protip: holding down Ctrl (Windows + Linux) or Command (Mac) and clicking your browser's back button will go back, but in a new tab.

# Changing files on your fork

Now that you have your own copy of this repository, you can make whatever changes you like. Try it out on the `README.md` file. Click on the file, then click "Edit" towards the top right. Change where the tutorial will be presented, credit yourself, credit me, credit the Flying Spaghetti Monster, do whatever you like.

Once you've made the changes that you want to make, scroll to the bottom. You'll see some other text entry boxes. These are for your commit message, describing the changes you've made. The first box is for the main description, which should be very concise, short enough to fit comfortably on one line. I don't say as concise as possible, because for historians "as concise as possible" may still be several pages. Save that for the second box, the extended description. This is where you can go into as much detail as you like about the changes you've made. By default, when you're editing your own repositories, you make your changes directly to what you're working on. Another option is to create a pull request, which lets you or someone else make a decision about whether to incorporate those changes later. We'll go into a bit more detail about this later. For now, just click "Commit changes"

Now that you've changed a file, you can see how you've affected its history. Click "History" at the top of the page. Here you'll see when I created the file, and your change to it. For a longer history, you can look at [the history for this tutorial](https://github.com/jaguillette/github_tutorial/commits/master/tutorial.md).

# Make it local, clone this repository

Something that GitHub is great at facilitating is keeping track of changes across multiple instances of the same repository. You can add a "remote" to an existing local git repo, or you can clone a repository from GitHub, which will come with the information about the remote version of the repo.

This is easier demonstrated than explained, so let's clone this repository locally. If you're on a Mac, or if you've downloaded and installed the software from [git-scm.com](http://git-scm.com), follow along through your Terminal (Mac) or Git Bash (Windows).

Go to the root of this repository by clicking on the repository name towards the top of the page. There, click "Clone or Download", click the URL in the text box, and copy it. Open a Terminal (Mac) or Git Bash (Windows), type `git clone ` (Don't forget the space at the end!) and paste the URL you copied (Cmd + Shift + V on Mac or Shift + Insert on Windows, as the normal Ctrl shortcuts do different things in terminals). Hit enter, and let it download!

At this point, if you're using Git for the first time, your command won't run, because Git wants to know who you are. Every commit you make is associated with your name and email, so if you haven't entered this information, Git will want it before it does anything else. This is independent from GitHub, and is necessary even if you only have a local Git repository. To set this up, enter the following commands with your own information instead of the example info:

    git config --global user.name "John Doe"
    git config --global user.email johndoe@example.com

Now, you still need to clone that repository. Rather than copying the url, typing the git clone command, and pasting the url in again, you can cycle through previous commands with the up and down arrow keys on your keyboard. Press up until you see the clone command again, then hit enter to have it run properly.

We could have set up the username and password beforehand, but...

1. That wouldn't be any fun
2. I want to demonstrate that charging into new things until you run headfirst into a problem is a viable strategy here. Git gives you the information that you need to resolve the problem, and once you do that, you're back on track. If you're doing anything with code and it breaks, most of the time it will give you information on how to resolve the problem. The response and solution won't always be this straightforward, but it's often actionable.

Anyways, now that you've cloned the repository, let's go there in the terminal. Your terminal is "pointing" at a single location, like having a folder open in Windows Explorer or Finder. Instead of clicking on a folder to move there, in terminal, we use the command `cd`, followed by the place we want to go. So in this case, type `cd github_tutorial`, since git clones repos into a folder with the repo name.

# Branches in Git

Branching in Git is a powerful and versatile capability. It allows you to maintain separate versions of your code in the same repository, so you can solve problems in a separate environment (un-break things without breaking everything else) or try out new ideas (while keeping a version of your files safe from your brilliant ideas). The default branch that repositories start on is called "master", and it's usually a good idea to have this as the most stable and canonical branch. You can always merge your fixes and new ideas back into "master" once you're sure that they don't break anything.

GitHub also uses this branching capability to power websites through [GitHub Pages](https://pages.github.com/). GitHub Pages use a branch, which is always called gh-pages. This repository actually has a gh-pages branch, with all of the files needed to set up a GitHub Pages site. When you make a new GitHub Pages site, you can easily make a single static front page from any of the templates available. However, the more powerful option is to make use of Jekyll, a Ruby Gem that GitHub uses to transform Markdown files into website pages (Ruby is a programming language, gems are libraries of code for that language that can be used to do cooler things easily). I've set up the gh-pages branch of this site to use Jekyll, and there are a variety of Jekyll themes that you can use to do the same, with some initial setup.

Let's switch to this branch. To appreciate what happens when you switch branches, type `ls` and hit enter. This command lists the files and folders in the directory that you're currently in. You should see `README.md`, `LICENSE.txt`, and `tutorial.md` file. Now type `git checkout gh-pages`, hit enter, then run `ls` again. Now you'll see a bunch of different files and folders! You can `git checkout master` if you want to convince yourself that the other files are still available, just go back to the gh-pages branch after.

# Editing local files

Now, let's make some local changes, creat a commit, and push that commit back up to GitHub. To start, let's open a file explorer in the current directory. On windows, use `explorer .`, and on Mac use `open .`. Now you'll see all of the files in the repository in an interface you're probably a bit more familiar with.

The site is currently populated with sample content from the Jekyll theme I started with ([Hyde](https://github.com/poole/hyde)). Let's modify the About page and push that change to the site. Again, it doesn't really matter how, but maybe add some fun facts, or change the ones already there. Let's also make a new file in this folder called `new-page.md` with a text editor like Notepad. Start this page with some basic information in a format called YAML. [YAML](http://yaml.org/) is an odd duck, and you don't need to know much about it to use it here. What you can do is copy the first four lines from `about.md` and change the title to "New Page". On a new line after the `---` line, you can start writing whatever Markdown you like, like a heading (`# New Page`) or some text.

Once you've made these changes with your favorite text editor (which will eventually be [SublimeText](https://www.sublimetext.com/)), we'll make a commit. First we have to "stage" the commit, to tell Git which files we want to include in this change. Let's see what we can do by running `git status` from the terminal. Here you'll see what files have had changes made to them. You'll see modified files, like `about.md`, as well as new, "untracked" files, like `new-page.md`. It's possible to just add all new and modified files, but we'll do them individually for now. `git add` is the command to stage a file for a commit, which is to say include the file in the change you're going to make. So `git add about.md` will stage `about.md` and `git add new-page.md` will add `new-page.md`.

Let's run `git status` again to see what we've done. You'll see now that there are "changes staged for commit". Since these look good, let's do the commit. The command for this is `git commit -m "the commit message"`. To add an extended description to the message, just hit enter twice before closing the quotation marks and then type to your heart's content before closing the quotation marks and hitting enter again.

# Pushing commits to GitHub

We have the commit now, so there's a record of the changes we've made. However, these changes are local, not on GitHub. This won't do, so we must "push" the changes up. The command for this in our case is `git push origin gh-pages`. `git push` is the base command, `origin` specifies the remote repository that changes are pushed to and pulled from, which is called "origin" by default, and `gh-pages` specifies the branch we're pushing to. If we were editing the `tutorial.md` file on the branch called "master", the command would be `git push origin master`. But for now, just run `git push origin gh-pages`. You'll be prompted for your GitHub credentials, so enter your username and then your password. Your password won't show up as you type for security reasons, but it's still accepting input.

With your changes pushed to GitHub, you'll have a website at _yourusername_.github.io/github_tutorial with the changes you've made. Congratulations!

# Pulling commits from GitHub

As the last thing we'll actually do with this repository, let's make another change on GitHub, then pull that change to our local repository. In the root of your GitHub repository on the default branch, "master" (github.com/_yourusername_/github_tutorial), create a new file by clicking "Create new file". Name it `done.md`, and type some congratulations to yourself for making it this far. You can use the default commit message on GitHub for creating a new file and just click "Commit changes" at the bottom of the page.

Now, back in the terminal window you've been using, switch to the default branch, "master" by running `git checkout master`. Run `git pull origin master` to pull the changes you made online, and run `ls` to make sure the new file is there. Congratulations! You've performed the tasks that comprise the majority of all work with Git! With this knowledge, you can clone project repositories, create repositories for your writing and track your changes, and even maintain a free website. Pat yourself on the back!

# But that's not all!

No more code to run, but there are some more useful features of GitHub that are worth mentioning.

## File Rendering

GitHub automatically renders certain file types, like GeoJson for mapping or STL for 3D models. There are probably some more that I don't know about, and they're constantly adding things to the site, so it's worth a quick search if there's some data that you want to quickly preview.

## We've got Issues

GitHub provides issue tracking for repositories that anyone can add. This provides a way for people who notice a problem with something in the repository to point it out, even if they don't know how to fix it. Issues can be tagged, discussed, and assigned to individuals. When the issue is fixed, it can be closed. Issues can also be referenced and closed by commit messages. For a more in-depth discussion, check out [the documentation](https://guides.github.com/features/issues/).

## Wikis

You can add a knowledge base for your project through GitHub's built-in wiki system. Especially for larger projects that use GitHub, it can be very useful to document information about the project and how to use or interact with it, so GitHub provides a way to do it. For more on wikis, here's some more [documentation](https://help.github.com/articles/about-github-wikis/).

## Pull Requests: Candy from strangers

A "pull request" is a way for someone who isn't the owner of a repository to contribute to it. While anyone can fork a repository, only the owner and people they specify can modify it. A pull request is a request to make a specific change to a file or files in the repository, and can be approved or denied by the owner or their designees. For more about pull requests, there's [some documentation](https://help.github.com/articles/using-pull-requests/), and also [a discussion](https://help.github.com/articles/using-pull-requests/) on StackOverflow, which is where pretty much everyone who writes code figures things out.

## Credit where credit is due, automatically

Every commit and every issue created or resolved counts as a contribution to GitHub, and these contributions are tracked automatically. You can see who's contributing how much to a project over time by looking at the Graphs for any given repository. The graphs are described more fully in [their introductory blog post](https://github.com/blog/1093-introducing-the-new-github-graphs).

## Last but not least, stars

Starring a repository indicates to others that you like a repository, and adds it to a collection of starred repositories that bookmarks the repository for you for later. Stars are also a great way to judge how popular a repository is. [This page](https://github.com/search?q=stars:%3E1&s=stars&type=Repositories) can show you the most popular repositories on GitHub right now, but a more useful way to look at stars is a way to sort search results. If you're looking for something in particular, sorting by stars can let you know which projects in your search results are most popular. This is useful for things like finding Wordpress or Jekyll themes that are popular with GitHub users, for example.

![The more you know](https://cdn.theatlantic.com/assets/media/img/mt/2014/09/The_More_You_Know/lead_large.png)
