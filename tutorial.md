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

# That wouldn't be any fun
# I want to demonstrate that charging into new things until you run headfirst into a problem is a viable strategy here. Git gives you the information that you need to resolve the problem, and once you do that, you're back on track. If you're doing anything with code and it breaks, most of the time it will give you information on how to resolve the problem. The response and solution won't always be this straightforward, but it's often actionable.
