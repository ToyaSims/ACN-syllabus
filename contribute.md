---
title: How to Contribute
---
# Contributing to ACN-syllabus

Ready to contribute? We'd love to have you on board. In this document we'll breeze through all the conventions in place. A lot of this stuff is really friggin important. We have to be very strict on the structure of this repo otherwise Tilde wont be able to consume it. Here are some guidelines we'd like you to follow so that everything can go smoothly, Ok. Let's get cracking!

-   [Choosing something to work on](#issues)
-   [Submitting a PR](#pr)
-   [Directory structure](#ds)
-   [Naming conventions](#nc)
-   [Static resources](#sr)
-   [A note on headings](#headings)
-   [Syllabus directory](#syllabus)
-   [Understanding the frontmatter](#frontmatter)
-   [Keys and values](#keys)
-   [Flavours](#flavours)
-   [Topic specific stuff](#topic)
-   [Project specific goodies](#goodies)
-   [Depricated and unimportant](#depricated)


## <a name="issues"></a> Choosing something to work on


The first thing you should do is go to our [issues](https://github.com/Umuzi-org/ACN-syllabus/issues ) and look for something you might be interested in working on. The issues have what we call labels that help us distinguish between available and claimed issues, issues that are simple or hard and issues for hactoberfest, it is important to look at those labels before claiming and issue, labels an issue might have are:
- status/help wanted
- status/issue-claimed
- good-first-issue
- hactoberfest and 
- experienced devs only

if an issue has the `status/issue-claimed` label please skip it and if you a beginner it is advisable to start with the issues that have the `good-first-issue` label. You can assign yourself an issue by commenting your name on the comment section inside the issue, if you feel you need help with choosing an issue or you unsure of anything you can join our [discord channel](https://discord.gg/3jRwWPm) and you will get all the help you need. 

## <a name="pr"></a> Submitting a PR

This syllabus is a Hugo based static site (for now). But on top of that, it is the configuration of our Tilde learning platform. You can see [Tilde](https://github.com/Umuzi-org/Tilde) for more.  

## <a name="ds"></a> Directory structure

In order to make this work, we need to be strict on the shape of the syllabus files. We have very specific naming and metadata conventions that contributors need to follow. We'll talk more about that later. But let's start by getting you set up :)

This video will walk you trough the whole process. Or you can just read the docs.

https://www.youtube.com/watch?v=j5-uaSgIGI0&feature=youtu.be

## To contribute

### <a name="nc"></a> Naming Conventions

## To clone this repo

There is a submodule in here so clone recursively:

- all the directory names are `words-seperated-with-dashes`
- all the markdown files are called `_index.md`


### <a name="sr"></a> Static resources

We're all about that high cohesion life. So if there is an image that has something to do with a specific \_index.md file, put it in the same directory as that file.

For example, look at this directory:

```
git clone --recursive git@github.com:Umuzi-org/ACN-syllabus.git
```

### <a name="headings"></a> A note on headings

This is a Hugo based application.

**PLEASE NOTE** We are using hugo version 0.51. We have run into some annoying problems when upgrading hugo in the past so please just use this version.
If you are tempted to give us a PR that upgrades this to the latest version of hugo, PLEASE DONT. The plan is to upgrade this all to use Eleventy in the near future.

### To get yourself set up on a Debian based machine (linux ubuntu/mint)

```
sudo apt install golang
./install_hugo.sh
```

### MAC

Add this in your bash file e.g .zshrc or .bashrc

```
# Go development
export GOPATH="${HOME}/.go"
export GOROOT="$(brew --prefix golang)/libexec"
export PATH="$PATH:${GOPATH}/bin:${GOROOT}/bin"
```

Run these installs in your terminal using Homebrew

```
<h1>Redux</h1>
<h2>Introduction</h2>
```

A heading and a subheading. Much nicer!


### <a name="syllabus"></a> Syllabus directory

This directory is a special case. It doesn't have `index.md` files but rather has different `.md` files representing the different learning paths people can go through.

- If a file name starts with `_` then that means it is a draft.
- Tilde basically looks for contentlinks. The order of the contentlinks matters of course
- Anything that isn't a contentlink will get ignored by Tilde
- There should be maximim one contentlink per line

## <a name="frontmatter"></a> Understanding the frontmatter

You'll see that every piece of content in this repo has an `\_index.md` file. Those files are broken down into 2 parts. Frontmatter and content.

The content is perfectly normal markdown.

The frontmatter is yaml. Yaml has it's own syntax. Indentation is super duper important with yaml.
For example, the two samples below mean very different things

```

### To run the development server, once it is installed

```
hugo serve -b "http://localhost:1313/"
```

That's it :) now you'll be able to poke around the main site

### Setting up and running the linter

Make sure you have Python3 installed. This wont work with legacy Python (python2.7 == legacy == dangerzone).

```
# make a virtual environment
python3 -m venv venv

### <a name="keys"></a> Keys and values

The frontmatter is basically a bunch of key-value pairs. Some of the values are lists, or further key-value pairs. Some are optional, some are not.

# activate it

#### <a name="simple"></a> The simple ones:

# install dependencies


#### <a name="flavours"></a> Flavours:

# and run the linter

The available flavours are specified in `available_flavours`.

#### <a name="topic"></a> Topic specific stuff

Then if you want to run the linter again, you dont need to do the whole setup again. Do this:

```
# activate your venv
source venv/bin/activate

#### <a name="goodies"></a> Project specific goodies

```

The linter starts off by looking over all the frontmatter and making sure that's fine. Then it builds the site and looks for trouble.

Some error messages are a bit funny looking. If you see something like this:

```
content/projects/django-airbnb-clone/users-can-crud-properties/_index.md has unrecognized frontmatter: reatdy
```

Then it means that there is a typo in the given file.

And then if you get a message like this:

```
public/syllabuses/data-eng-boot/index.html:  <span class="contentlink-missing" data="topics/intro-to-tilde"
```

#### <a name="depricated"></a> Depricated and unimportant

## Syllabus Content

Look inside the content directory. The documentation is composed of a bunch of markdown files (all named `_index.md`) with a lil metadata. Ok, a lot of metadata.

