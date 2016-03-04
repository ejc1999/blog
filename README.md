# base-python
This is the base of a blogging website written in Python

## Setting Up Locally

Our end goal is to have our very own blog website that we can write posts on. The first step to having a website running on the Internet is to get one running on your local machine. No one will be able to access it, but at least you'll know it works.

To get the Python based blog up and running locally we'll first need to grab a copy of the base code from Github. Here's [a link](https://github.com/CodeGuild-co/base-python/archive/master.zip). Download this zip file and unzip it onto the Desktop.

The unzipped folder is called `base-python-master` that's not particularly descriptive, change it to something nicer. I called mine `blog`.

We now have the code but we can't run it because we haven't installed the software dependencies. Let's do that. Open a `Konsole` window and type the following commands (don't type the `$` symbol, that's to show you that we're looking at a `Konsole` command line):

    $ sudo apt-get install curl
    $ curl https://bootstrap.pypa.io/get-pip.py | sudo python3

Those commands installed a lovely piece of software called `pip`, we can use `pip` to download the Python libraries that we need to run our blog:

    $ cd Desktop/blog
    $ pip install -r requirements.txt

This will churn away for a while downloading things. When it's done you should be able to run the blog website like this:

    $ python3 blog/blog.py

You should now be able to open up a browser and visit http://localhost:5000 to see your blog. When you make changes to the files, refresh the page to see the website change.

## Saving Your Work

Once you've made some changes you'll want to save them. As well as saving them to your USB stick, you should save your projects in "the cloud". More accurately, you should save your code in a version control system. For this project we'll use `git`, and GitHub.

First, download `git`:

    $ sudo apt-get install git

Then set up `git` to use your name and email address:

    $ git config --global user.name "YOUR NAME"
    $ git config --global user.email "YOUR EMAIL ADDRESS"

Now visit [GitHub](https://github.com) and create an account (it's free).

In GitHub create a new repository by clicking the plus symbol in top-right of the page. Don't check the "Initialize this repository with a README" checkbox.

Let's save our local code to this new GitHub repository:

    $ git init
    $ git add .
    $ git commit -m "First commit"
    $ git remote add origin https://github.com/USERNAME/REPO.git
    $ git push -u origin master

You'll have to change `USERNAME` and `REPO` to match your username and repository name.

You're all done!

Anytime you want to save future changes you'll only need to run:

    $ git add .
    $ git commit -m "MESSAGE DESCRIBING YOUR CHANGES"
    $ git push origin master

## Getting Online

Once you've played around with your blog locally you'll want to put it on the internet for other people to see. Here's how:

1. Signup to [Heroku](heroku.com) (it's free)
2. Ask Billy to create an app for you and share it with your Heroku account
3. Connect your Heroku account to your Github account
4. Connect your Heroku app to your Github repo
5. Enable automatic deploys
6. Make a change to your repo (using the Github editor)
7. Visit your Heroku app's settings and add a custom domain
    - add your personal CodeGuild domain
    - e.g. `wm.codeguild.co`
8. Visit your domain and see your blog!


## Adding Posts

Simply add a new HTML file in the `blog/templates/posts` directory and then link to it it the `blog/templates/home.html` file.

It's easy, but boring. You should try using Python to automate these steps (be lazy!).
