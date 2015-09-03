# My Banging OSX Dev Config

A selection of install and setup notes for my dev config on OSX, this is somewhat incomplete at the moment but will eventually contain all of the bits and pieces to get going quickly.  Other than instructions this also includes my sublime text setup, and will in time be the home of any other config files such as the JSCS json file etc.

## Table Of Contents
<!-- MarkdownTOC depth=3 link=true-->

- Apps
    - Alfred
    - xcode
    - Sublime Text
    - iTerm2
    - RoboMongo
    - Sequel Pro
    - Tower 2
- Command Line
    - Brew
    - Git
    - YADR
    - Cheat
    - Node & NPM
    - Grunt, Bower & Gulp CLI's
    - Composer
    - Git Extras
    - Sublime Text Dependancies
- Frameworks
    - Meteor
    - Laravel  & Lumen
- Environment
    - MySQL
    - MongoDB
    - Docker ToolBox
    - VirtualBox
    - Vagrant
    - Homestead
- SSH keys

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
 
````bash
    sudo ln -sf "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/bin/subl
````

##### Pre-Configured Setup
To use  the setup in this repo for sublime text, do the following : 

````bash
    // TODO : add ln cmd  to dev config repo
````

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



### Tower 2
a powerful commercial app and GUI for working with Git. [available here](http://www.git-tower.com/)



## Command Line
After installing iterm above, a number of these tools are neccessary for a) a better OSX experience, and b) general purpose web development.

* Yadr
* brew
* git
* cheat
* node & npm
* grunt, gulp  and bower cli's
* composer
* git-extras
* wp-cli

### Brew 
Brew is the dependancy manager for OSX and should be used to install most development tools. isntall it by running the following: 

````bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
````

[homebrew](http://brew.sh/)

### Git

````bash
    brew install git
````
You will also want to setup your Git and GitHub user details

````bash
    //- Setting user name and email globally in git
    git config --global user.name "Your Name Here"
    git config --global user.email "you@youremail.com"
    
    //-  GitHub token config
    git config --global github.user YOURUSERNAME
    git config --global github.token 0123456789abcdef0123456789abcdef
````

### YADR
 follow the instructions here to install the the toys for terminal : 

````bash
    sh -c "`curl -fsSL https://raw.githubusercontent.com/skwp/dotfiles/master/install.sh`"
````

[YADR](https://github.com/skwp/dotfiles)

#### custom VIM plugins
TODO

### Cheat
cheat allows you to create and view interactive cheatsheets on the command-line. It was designed to help remind *nix system administrators of options for commands that they use frequently, but not frequently enough to remember.

````bash
    brew install cheat
````

[cheat](https://github.com/chrisallenlane/cheat)


### Node & NPM
To install node and npm via brew run : 

````bash
brew install node
````

to check that node is install run : 

````bash
node -v
````

and check that NPM is installed 

````bash
npm -v
````

to upgrade to a new version first run `brew update` and then run `brew upgrade node`.  You may want to install "n" or "nvm" to manage multiple version of node.

[Node.js](https://nodejs.org/)


### Grunt, Bower & Gulp CLI's
Grunt and Gulp are javascript task runners, bower is a tiny front end dependancy managment tool based on git.

to install the grunt cli 

````bash
npm install -g grunt-cli
````

for gulp : 

````bash
npm install --global gulp
````

for bower : 

````bash
npm install -g bower
````

[grunt js](http://gruntjs.com/)
[gulp js](http://gulpjs.com/)
[bower](http://bower.io/)


### Composer
Composer is a tool for dependency management in PHP. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you.

First get the composer.phar file

````bash
   curl -sS https://getcomposer.org/installer | php
````

them move it to your bin directory, renaming it to just composer

````bash
    mv composer.phar /usr/local/bin/composer
````

[composer](https://getcomposer.org/)



### Git Extras
Great set of GIT utilities -- repo summary, repl, changelog population, author commit percentages and more

````bash
    brew install git-extras
````

[git-extras](https://github.com/tj/git-extras)

### Sublime Text Dependancies
The linter packages in particular will require these dependancies in order to work.

````bash
    // eslint
        npm install -g eslint
    // jshint
        
````



## Frameworks
These are the frameworks we use that require some pre existing setup, note that for laravel and lumen it is reccommended to use the homestead vagrant development environment disucssed below in the frameworks section.

* Meteor
* laravel & Lumen



### Meteor
Meteor is a complete open source isomorphic reactive platform for building web and mobile apps in pure JavaScript.

````bash
    curl https://install.meteor.com/ | sh
````

Read more here on the [Meteor Website](https://www.meteor.com/)



### Laravel  & Lumen
The PHP Framework For Web Artisans

````bash
    composer global require "laravel/installer=~1.1"
````

Make sure to place the ~/.composer/vendor/bin directory in your PATH so the laravel executable can be located by your system.

Read the laravel docs [here](http://laravel.com/docs/5.1)

##### Lumen
Lightning fast micro-services and APIs (based on Laravel, can be migrated to laravel)

````bash
    composer global require "laravel/lumen-installer=~1.0"
````

Make sure to place the ~/.composer/vendor/bin directory in your PATH so the lumen executable can be located by your system. (as above)

Read the laravel docs [here](http://lumen.laravel.com/docs/installation)



## Environment
Our latest approach to a development environment is to focus on virtualization either via docker or vagrant.

* MySQL
* MongoDB
* Docker Toolbox
* virtualbox (should be installed with docker Toolbox)
* vagrant
* Homestead


### MySQL

Next we need to install MySQL. Yes, it's really this easy ... but this will take a while.

    brew install mysql

Now to warm it up:

    mysql_install_db

After you run `mysql_install_db` you'll see output like this ...

    Installing MySQL system tables...
    OK
    Filling help tables...
    OK

    To start mysqld at boot time you have to copy
    support-files/mysql.server to the right place for your system

    PLEASE REMEMBER TO SET A PASSWORD FOR THE MySQL root USER !
    To do so, start the server, then issue the following commands:

    ./bin/mysqladmin -u root password 'new-password'
    ./bin/mysqladmin -u root -h AS-MBP15.local password 'new-password'

    Alternatively you can run:
    ./bin/mysql_secure_installation

    which will also give you the option of removing the test
    databases and anonymous user created by default.  This is
    strongly recommended for production servers.

    See the manual for more instructions.

    You can start the MySQL daemon with:
    cd . ; ./bin/mysqld_safe &

    You can test the MySQL daemon with mysql-test-run.pl
    cd ./mysql-test ; perl mysql-test-run.pl

    Please report any problems with the ./bin/mysqlbug script!

When that's done, make sure MySQL automatically starts on login:

    launchctl load -w /usr/local/Cellar/mysql/VERSION/com.mysql.mysqld.plist

### MongoDB

````bash
    brew install mongodb
````

### Docker ToolBox
Docker Toolbox installs all of the docker tools, including machine(to run docker locally), compose, kitematic (a GUI),  and VirtualBox to make working wtih docker locally much easier.



### VirtualBox
VirtualBox is a general-purpose full virtualizer for x86 hardware, targeted at server, desktop and embedded use.

Download separately [here.](https://www.virtualbox.org/wiki/Downloads)



### Vagrant
Create and configure lightweight, reproducible, and portable development environments.

Download and install vagrant [here.](https://www.vagrantup.com/)



### Homestead
Homestead is a vagrant box designed for general purpose development with laravel, but provides a solid environment for wordpress or other php development as well.



## SSH keys

Generating SSH keys (OSX)

First check to see if a ssh key directory exists.

    cd ~/.ssh
    ls -lash

If nothing is listed, then you can move on - or else you'll need to backup the existing key and create a new as needed.

    ssh-keygen -t rsa -C "adam@stacoviak.com"
