---
title: "A step-by-step guide: Jekyll Netlify CMS"
categories: articles
cmsUserSlug: ""
date: 2015-11-06 12:00:00
---

### **Welcome to Netlify**
*Something about jekyll netlify CMS and why it's good to start with a template like this.*

### **Setup your GitHub Repository**

#### 1. Get your own copy.
Fork it online to your github account and rename from netlify-jekyll-cms to my-repo-name.

#### 2. Local Work Space.
Make a directory locally, open terminal and go to this location (cd my-local-repo-directory).

#### 3. Get Repository URL
![a1_remotegithuburl.png](/uploads/a1_remotegithuburl.png)

From the repo you made in point 1, clone it to your local directory. First, get the repo-url and second, use it in the following line instead of my-repo-url (it will look like https://github.com/AccountName/RepoName.git or similar):
```
$ git clone my-repo-url .
```
The full stop "." at the end specifies the current folder as the checkout folder, so make sure you are in the correct folder.

#### 4. Install the Netlify Git API.
Go to the [Netlify Git API](https://github.com/netlify/netlify-git-api/releases) releases page and download the relevant version for your OS.
* On Linux: decompress the netlify-cms-api file and add it to your path. E.g. this can be done by using the command below from the directory where you have the file and it will move the executable to your bin directory, which is a part of the PATH:
```
$ sudo mv netlify-git-api '/bin'
```
* On Mac: *we will add description here*
* On Windows: *we will add description here*

#### 5. Set up your gemfile
We want to use Jekyll 3.0.0 and since we're using github, we will also add the github pages plugin. To do this, we open the gemfile in the root directory and change/add the following:
```
gem 'jekyll', '~> 3.0.0'
gem 'jekyll-sitemap'
```
At the time of writing the jekyll used for the template was 2.5.3, but we're having no issues with the newer version of Jekyll so far, so we're going ahead.

#### 6. Bundle Install.
The following command will install the jekyll gem specified in the gemfile, along with github-pages, since we just specified this in the gem file:
```
$ bundle install
```
Once you've used the command above, to install the listed gems, a gemfile.lock file will be created in your directory. This makes sure that netlify uses the same version of Jekyll (and whatever else you specified in the gemfile) that you used to build your site.

#### 7. Start Netlify CMS Server
From your newly cloned repo working in local directory run the following command, for each user you wish to add (you will be asked for an email, a name and a password):
```
$ Next we need to start Netlify CMS with the following command:
```
$ netlify-git-api serve
```
This will start the Netlify CMS Server.

**Keep the Terminal Window/Command Prompt open to keep the server running!**

You can log in here and create a new post: 
[https://localhost:4000/admin](https://localhost:4000/admin)

#### 8. Build and Watch 
From the root of your site, run the following command to build your site using bundle
```
$ bundle exec jekyll server --watch
```
Now you can navigate to check out your site and the post you just created through this link:
[https://localhost:4000](https://localhost:4000)

#### 9. Push to Github
Once you're done fiddling with the local version and maybe adding some posts, we should try out this netlify-cms online.
In the terminal window/command prompt, CD to the root folder of your site and start by entering this command, to check where the project is pushed to:
```
$ git remote -v
```