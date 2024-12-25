---
title:  Build and host portfolio site with jekyll chirpy - Part 1 | Prepare Local Environment
date: 2023-09-18 12:34:27 -500
categories: [portfolio]
tags: [portfolio,personal site,cv]
---

## Objective of this article
we are going to understand how to build and host portfolio site with jekyll-chirpy.
<br>

This is the first part of a 4 part series article and we will understand :

1. How to set up local Environment for Ruby 
2. How to use Chirpy theme and run it locally and deploy to GitHub pages
3. How to add a comment section for each post using `giscus`
4. How to add custom domain name to our portfolio website

We will use chirpy as a theme, and host this static site to GitHub. In the first part we will understand how to prepare our local environment to get started.


## Why we are using jekyll
jekyll is open-source static site generator, and it also has a very good integration with GitHub Pages. If you already have a ruby development setup installed in your local machine then it is very easy and fast to run anything with jekyll locally. And there is a ton of theme out there which are opensource and easy to get started.


## How to Prepare local development environment to get started
In this article we will only discuss how to set up in the **MAC environment**. Setup in Linux and windows is also very simple. 

First , we need to check if we already have ruby installed
```bash
which -a ruby
```
if we see something like this as output 
```text
/usr/bin/ruby
```
that means we already have ruby installed in our machine.

As the system Ruby is old, and it can’t be updated we will not use the ruby that is already installed , instead we will set up latest version of ruby and then work with it.


we can set up ruby in a lot of different ways but my recommendation is to use a ruby version manager tool like [rbenv](https://github.com/rbenv/rbenv). Also with `rbenv` we can switch between multiple Ruby versions on the same machine if needed.

So, lets setup `rbenv` and for that we need to run the below three commands

```bash
brew install rbenv ruby-build
vi ~/.zshrc 
eval "$(rbenv init - zsh)"
```
Now let's understand what these command does. <br>
- This command `brew install rbenv ruby-build` installs the `rbenv` into our local machine and we are using `Homebrew`
- The next two commands ensure that `rbenv` is properly configured every time we start a new `zsh` session.So, when we run this command `vi ~/.zshrc`, we are opening the configuration file of `zsh` with `vim` and after that we need to add this line `eval "$(rbenv init - zsh)` to the `.zshrc` file.

If you are using `bash` then the commands looks like below
```bash
brew install rbenv ruby-build
vi ~/.bashrc
eval "$(rbenv init - zsh)"
```
<br>
Now let's install Ruby. And for that we need to run these commands

```bash
rbenv install -l
rbenv install 3.2.2 --verbose
```
Now let's understand what these command does. <br>
- `rbenv install -l` shows all the latest stable ruby version, and we can choose what we want to install. At the time of writing this article we have ruby version : `3.2.2` and we are going to install ruby with the second command `rbenv install 3.2.2 --verbose`

When we install Ruby , `Ruby Gems` also gets installed. `Ruby Gems` or `gem` is a command-line tool for installing different packages or libraries that can be used in Ruby applications.
<br>

Now its time to install `bundler` and `jekyll`. These are two ruby gems or libraries that we are going to use for our static site.

```bash
gem install bundler jekyll
```

Let's verify that all the dependency are installed.
```bash
gem env home
which -a gem
which -a ruby
```
when the first command `gem env home` is run then, we should see something as output
```bash
/Users/YOUR_USER_NAME/.rbenv/versions/3.2.2/lib/ruby/gems/3.2.0
```

And that means we have ruby setup in our local machine.
<br>
we can also verify even further with the last 2 commands

For this command `which -a gem`, the output should be

```bash
/Users/YOUR_USER_NAME/.rbenv/shims/gem
```

For this command `which -a ruby`, the output should be

```bash
/Users/YOUR_USER_NAME/.rbenv/shims/ruby
```



And that's it , so now we have all the component we need to continue building our static site.

{% include comment.html %}
