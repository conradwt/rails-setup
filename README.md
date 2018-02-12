Rails Setup Guide For macOS
=============================

The purpose of this step by step tutorial is to provide a very simple example of configuring a minimal Rails environment.

# Software Requirements

- macOS 10.13.3 or later

## Installation Steps

1) download and install Xcode from Mac App Store

  [Download Xcode](https://itunes.apple.com/us/app/xcode/id497799835?mt=12#)

2) from the Terminal.app, install command line tools

  ```
  $ xcode-select --install
  ```

3) download and install MacPorts for OS X

  [Download MacPorts](https://github.com/macports/macports-base/releases/download/v2.4.2/MacPorts-2.4.2-10.13-HighSierra.pkg)

4) download and install Node

  [Download Node](https://nodejs.org/dist/v9.5.0/node-v9.5.0.pkg)

5) open Disk Utility, select MacIntosh HD, click Repair Disk Permissions

6) open the Terminal.app


7) remove existing environment initialization files

  ```
  $ mv ~/.bashrc ~/.bashrc.orig
  $ mv ~/.bash_login ~/.bash_login.orig
  $ mv ~/.bash_profile ~/.bash_profile.orig
  $ mv ~/.profile ~/.profile.orig
  $ mv ~/.zshrc ~/.zshrc.orig
  ```

  Note: Some or most of the above files may not exist.  Thus, if you get the
        following error it's OK:

        e.g.  mv: rename .bashrc to .bashrc.orig: No such file or directory

8) clone this repository

  ```
  $ git clone https://github.com/conradwt/rails-setup-guide-for-macos
  ```

9) change directory to the cloned repository

  ```
  $ cd path/rails-setup-guide-for-macos
  ```

10) install RBenv

  ```
  $ git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
  ```

11) install all of the approved plugins RBenv plugins

  ```
  $ chmod +x install-rbenv-plugins.sh
  $ ./install-rbenv-plugins.sh
  ```

12) install Ruby 2.4.3

  ```
  $ rbenv install 2.4.3
  $ rbenv global 2.4.3
  ```

13) install Rails 5.1.4

  ```
  $ gem install bundler
  $ gem install rails -v 5.1.4
  $ rbenv rehash
  ```

14) configure the .profile

  ```
  $ cp sample.profile $HOME/.profile
  $ . ~/.profile
  ```

  Note:  If you see the following message,

  ```
  **-bash: rbenv: command not found**
  ```

  please continue to the next step.

15) set the Git completion

  ```
  $ cp sample.git-completion.sh $HOME/.git-completion.sh
  ```

16) install required ports from MacPorts

  ```
  $ chmod +x install-ports.sh
  $ ./install-ports.sh
  ```

17) install Heroku Toolbelt

  [Download Heroku Toolbelt](https://toolbelt.heroku.com)

18) open Disk Utility, select MacIntosh HD, click Repair Disk Permissions

19) set the terminal

  ```
  $ cp sample.terminal $HOME/.
  ```

20) from the terminal menu, Shell -> Import, select sample.terminal file

  ```
  Terminal -> Preferences -> Settings, click the 'sample' profile on the left, click Default
  ```

21) create a Github.com account

  ```
  Note:  Skip this step if you already have an account.
  ```

22) create Git configuration file

  ```
  $ cp sample.gitconfig ~/.gitconfig
  ```

23) edit the Git configuration file

  ```
  $ atom ~/.gitconfig
  ```

  Note: `atom` editor is being used but you can use any editor to make the
        modifications to the `.gitconfig` file.  

  change the text on the right side of the equal:

	  name = <your firstname lastname>
	  email = <your e-mail address>

  to the text for your `name` and `e-mail` that you're using for Github.com:

    e.g.

    name = John Doe
    email = john.doe@example.com

24) set up PostgreSQL Server

  ```
  $ sudo mkdir -p /opt/local/var/db/postgresql10/defaultdb
  $ sudo chown postgres:postgres /opt/local/var/db/postgresql10/defaultdb
  $ sudo su postgres -c '/opt/local/lib/postgresql10/bin/initdb -D /opt/local/var/db/postgresql96/defaultdb'
  ```

25) set PostgreSQL 96 as the default version

  ```
  $ sudo port select postgresql postgresql10
  ```

26) start the PostgreSQL 10 Server

  ```
  $ pgstart
  ```

$ = stuff that you type in the terminal

## Support

Bug reports and feature requests can be filed for the <add project here> project here:

* [File Bug Reports and Features](https://github.com/conradwt/rails-setup-guide-for-macos/issues)

## Contact

Follow Conrad Taylor on Twitter ([@conradwt](https://twitter.com/conradwt))

## Creator

- [Conrad Taylor](http://github.com/conradwt) ([@conradwt](https://twitter.com/conradwt))

## License

This repository is released under the [MIT License](http://www.opensource.org/licenses/MIT).

## Copyright

&copy; Copyright 2014 - 2018 Conrad Taylor. All Rights Reserved.
