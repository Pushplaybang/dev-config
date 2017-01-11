# My Banging OSX Dev Config

A selection of install and setup notes for my dev config on OSX, this is somewhat incomplete at the moment but will eventually contain all of the bits and pieces to get going quickly.  Other than instructions this also includes my sublime text setup, and will in time be the home of any other config files such as linters etc json file etc.

## Table Of Contents
<!-- MarkdownTOC depth=3 link=true-->

1. [Apps](#apps)
    1. [Alfred](#alfred)
    1. [xcode](#xcode)
    1. [Sublime Text](#sublime-text)
    1. [iTerm2](#iterm2)
    1. [RoboMongo](#robomongo)
    1. [Sequel Pro](#sequel-pro)
    1. [Tower 2 \(commercial\)](#tower-2-commercial)
    1. [Pixate](#pixate)
    1. [Sketch \(commercial\)](#sketch-commercial)
1. [Command Line](#command-line)
    1. [Brew](#brew)
    1. [Brew Cask](#brew-cask)
    1. [Git](#git)
    1. [YADR](#yadr)
    1. [Cheat](#cheat)
    1. [Node & NPM](#node--npm)
    1. [n](#n)
    1. [Grunt, Bower & Gulp CLI's](#grunt-bower--gulp-clis)
    1. [Composer](#composer)
    1. [Git Extras](#git-extras)
    1. [Local Tunnel](#local-tunnel)
    1. [Sublime Text Dependancies](#sublime-text-dependancies)
    1. [Ruby](#ruby)
    1. [Global Packages & Dependancies](#global-packages--dependancies)
        1. [ImageMagick and GraphicsMagick](#imagemagick-and-graphicsmagick)
        1. [CodeClimate CLI](#codeclimate-cli)
1. [Frameworks](#frameworks)
    1. [Meteor](#meteor)
        1. [Developing Unpublished Meteor Packages](#developing-unpublished-meteor-packages)
    1. [Laravel & Lumen](#laravel--lumen)
    1. [Jekyll](#jekyll)
1. [Environment](#environment)
    1. [MongoDB](#mongodb)
    1. [Docker](#docker)
1. [SSH keys](#ssh-keys)
    1. [SSH Config](#ssh-config)
    1. [PHP in sublime text](#php-in-sublime-text)

<!-- /MarkdownTOC -->


## Apps
These are the general purpose apps I use daily. Your mileage may vary.

* Alfred
* xcode + cmd line tools
* sublime text
* iterm2
    * with yaddir, zsh, and solarized theme (installed below under the command line section)
* Robomongo
* Sequel Pro
* Tower 2



### Alfred
Alfred is a handly little tool that providesd a lot of utility, similar to spotlight, but far more awesome, you can launch apps, find files, trigger a google search, do quick calculation simply by hitting `alt+space` further reducing the need for mousing around OSX.



### xcode
xcode is the Apple development environment, and can be installed through the app store.  It includes a number of useful utilities and general purpose tools such as git.

check out [xCode here](https://developer.apple.com/xcode/)



### Sublime Text
Sublime Text is a sophisticated text editor that can be installed here [sublime text 3 here](http://www.sublimetext.com/3)

##### opening files and folders from the cmd line with sublime
Sublime includes a cli tool called **subl**. in order to use it we need to create a symlink in our usr/bin directory from the sublime application folder so that we can call this command anywhere while in terminal.  to do this :

```sh
    sudo ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl
```

##### Pre-Configured Setup
To use  the setup in this repo for sublime text, do the following :

```sh
    // TODO : add ln cmd  to dev config repo
```

**NB** : This setup includes JSCS which is set to auto format your JS files on save, you'll need to navigate to `preferences->Package Settings->JSCS Formatter->User - Settings` and change the path to the jscs.json file as per the location of this repository.

##### Font
This setup specifies the **fira mono font** by mozilla whitch is included in the repo, and can be installed like as per usual.

##### Dependancies
There are some small dependancies that are required for some sublime packages to function properly, these are listed under the command line setup below.



### iTerm2
iTerm2 is a replacement for Terminal and the successor to iTerm. It works on Macs with OS 10.5 (Leopard) or newer. iTerm2 brings the terminal into the modern age with features you never knew you always wanted.  It can be downloaded here [iterm website](https://www.iterm2.com/index.html)



### RoboMongo
Shell centric corss platform MongoDB management tool [download here](http://robomongo.org/)



### Sequel Pro
A small open source app for working with SQL db's, can be [downloaded here](http://www.sequelpro.com/download)



### Tower 2 (commercial)
a powerful commercial app and GUI for working with Git. [available here](http://www.git-tower.com/)


### Pixate
a great app for building mobile prototypes, owned by google.
available from there [website](http://www.pixate.com/getstarted/)


### Sketch (commercial)
Great web design and vetor tool [available here](https://www.sketchapp.com/ )




## Command Line
After installing iterm above, a number of these tools are neccessary for a) a better OSX experience, and b) general purpose web development.

* Yadr
* brew
* brew cask
* git
* cheat
* node & npm
* grunt, gulp  and bower cli's
* composer
* git-extras
* wp-cli

### Brew
Brew is the dependancy manager for OSX and should be used to install most development tools. isntall it by running the following:

```sh
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

[homebrew](http://brew.sh/)



### Brew Cask
Homebrew Cask extends Homebrew and brings its elegance, simplicity, and speed to OS X applications and large binaries alike.

```sh
brew install caskroom/cask/brew-cask
```

```sh
brew cask alfred link
```




### Git
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

```sh
    brew install git
```
You will also want to setup your Git and GitHub user details

```sh
    //- Setting user name and email globally in git
    git config --global user.name "Your Name Here"
    git config --global user.email "you@youremail.com"

    //-  GitHub token config
    git config --global github.user YOURUSERNAME
    git config --global github.token 0123456789abcdef0123456789abcdef
```

### YADR
 follow the instructions here to install the the toys for terminal :

```sh
    sh -c "`curl -fsSL https://raw.githubusercontent.com/skwp/dotfiles/master/install.sh`"
```

[YADR](https://github.com/skwp/dotfiles)



### Cheat
cheat allows you to create and view interactive cheatsheets on the command-line. It was designed to help remind *nix system administrators of options for commands that they use frequently, but not frequently enough to remember.

```sh
    brew install cheat
```

[cheat](https://github.com/chrisallenlane/cheat)



### Node & NPM
To install node and npm via brew run :

```sh
brew install node
```

to check that node is install run :

```sh
node -v
```

and check that NPM is installed

```sh
npm -v
```

to upgrade to a new version first run `brew update` and then run `brew upgrade node`.  You may want to install "n" or "nvm" to manage multiple version of node.

[Node.js](https://nodejs.org/)


### n
The simplest version manager for node

```sh
npm install -g n
n stable
```



### Grunt, Bower & Gulp CLI's
Grunt and Gulp are javascript task runners, bower is a tiny front end dependancy managment tool based on git.

to install the grunt cli

```sh
npm install -g grunt-cli
```

for gulp :

```sh
npm install --global gulp
```

for bower :

```sh
npm install -g bower
```

[grunt js](http://gruntjs.com/)
[gulp js](http://gulpjs.com/)
[bower](http://bower.io/)



### Composer
Composer is a tool for dependency management in PHP. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you.

First get the composer.phar file

```sh
   curl -sS https://getcomposer.org/installer | php
```

them move it to your bin directory, renaming it to just composer

```sh
    mv composer.phar /usr/local/bin/composer
```

[composer](https://getcomposer.org/)



### Git Extras
Great set of GIT utilities -- repo summary, repl, changelog population, author commit percentages and more

```sh
    brew install git-extras
```

[git-extras](https://github.com/tj/git-extras)



### Local Tunnel
Localtunnel allows you to easily share a web service on your local development machine without messing with DNS and firewall settings.  Localtunnel will assign you a unique publicly accessible url that will proxy all requests to your locally running webserver.

```sh
npm install -g localtunnel
```

(Local Tunnel Website)[http://localtunnel.me/]



### Sublime Text Dependancies
The linter packages in particular will require these dependancies in order to work.

```sh
  // eslint
  npm install -g eslint
  npm install -g babel-eslint
  npm install -g eslint-plugin-react
```

You'll then want to setup an `.eslintrc` file, and if you'd like to use the one defined here, you'll need to install the airbnb eslint config locally as it extends it..

```sh
npm install - g eslint-config-airbnb
```

### Ruby
Like many things on mac, there is a system version of this, but to avoid potentially screwing that up and continually dealing with permission issues on the system version, install it with rbenv.  (You could alternatively use RVM)

```sh
  brew install rbenv ruby-build
  rbenv install -l
  rbenv install 2.2.3
```



### Global Packages & Dependancies

#### ImageMagick and GraphicsMagick
used for processing images.

```sh
brew install graphicsmagick
brew install imagemagick --with-webp
```


#### CodeClimate CLI
if you're planning to use the codeClimate static analysis, the cli can be helpful, check out [codeclimate here](https://codeclimate.com/dashboard)

```sh
brew tap codeclimate/formulae
brew install codeclimate
```



## Frameworks
These are the frameworks we use that require some pre existing setup, note that for laravel and lumen it is reccommended to use the homestead vagrant development environment disucssed below in the frameworks section.

* Meteor
* laravel & Lumen



### Meteor
Meteor is a complete open source isomorphic reactive platform for building web and mobile apps in pure JavaScript.

```sh
    curl https://install.meteor.com/ | sh
```

Read more here on the [Meteor Website](https://www.meteor.com/)

#### Developing Unpublished Meteor Packages
To work with unpublished meteor packages locally, there are two methods.  a) you can symlink them into the `packages` folder of each project, or b) you can augment the global `$PACKAGE_DIRS` var as is discussed in this [stackoverflow question and answer](http://stackoverflow.com/questions/29289316/how-to-share-private-meteor-packages-between-multiple-projects).

```sh
   export PACKAGE_DIRS=$PACKAGE_DIRS:$HOME/repos/meteor-packages
```



### Laravel & Lumen
The PHP Framework For Web Artisans

```sh
    composer global require "laravel/installer=~1.1"
```

Make sure to place the ~/.composer/vendor/bin directory in your PATH so the laravel executable can be located by your system.

Read the laravel docs [here](http://laravel.com/docs/5.1)



##### Lumen
Lightning fast micro-services and APIs (based on Laravel, can be migrated to laravel)

```sh
    composer global require "laravel/lumen-installer=~1.0"
```

Make sure to place the ~/.composer/vendor/bin directory in your PATH so the lumen executable can be located by your system. (as above)

Read the laravel docs [here](http://lumen.laravel.com/docs/installation)



### Jekyll
a super simple static site generator, that works with plain text and markup.

```sh
    gem install jekyll
```





## Environment
Our latest approach to a development environment is to focus on virtualization either via docker or vagrant.

* MongoDB
* Docker Toolbox
* virtualbox (should be installed with docker Toolbox)
* vagrant
* Homestead





### MongoDB
By offering the best of traditional databases as well as the flexibility, scale, and performance required by today’s applications, MongoDB lets innovators deploy apps as big as they can possibly dream. From startups to enterprises, for the modern and the mission-critical, MongoDB is the database for giant ideas.

```sh
    brew install mongodbsudo mkdir -p /data/db
    sudo mkdir -p /data/db
    sudo chown -R `whoami`: data
```

(MongoDB Website)[https://www.mongodb.com/]



### Docker
Docker Toolbox installs all of the docker tools, including machine(to run docker locally), compose, kitematic (a GUI),  and VirtualBox to make working wtih docker locally much easier.



## SSH keys

Generating SSH keys (OSX)

First check to see if a ssh key directory exists.

    cd ~/.ssh
    ls -lash

If nothing is listed, then you can move on - or else you'll need to backup the existing key and create a new one as needed.
```sh
    ssh-keygen -t rsa -C "guy@youremail.com"
```

### SSH Config
To create easy to identify aliases for your hosts that you access via ssh you'll want to crete a `config` in your `.ssh/` directory. then for each add the following:

```sh
Host <name-of-host>
  HostName <ip-address>
  Port 22
  User root
  IdentityFile ~/.ssh/id_rsa
```

Port, user and id file should also be set appropriately.












### PHP in sublime text
https://philsturgeon.uk/php/2013/08/20/php-static-analysis-in-sublime-text/
