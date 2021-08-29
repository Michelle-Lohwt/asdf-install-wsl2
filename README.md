# Install asdf (ruby, nodejs and yarn) in WSL2
This repository serves to help those who need to install `asdf` using `WSL2` and we will be installing `ruby`, `nodejs` and `yarn` using `asdf`<br><br>
Author: Michelle Loh <br>
Update Date: 29/8/2021 <br>
Created Date: 29/8/2021 <br>

---
## Table of Contents
1. [What is WSL2](https://github.com/Michelle-Lohwt/asdf-install-wsl2#what-is-wsl2)
2. [What is asdf](https://github.com/Michelle-Lohwt/asdf-install-wsl2#what-is-asdf)
3. [Install WSL2](https://github.com/Michelle-Lohwt/asdf-install-wsl2#install-wsl2)
4. [Before installing asdf](https://github.com/Michelle-Lohwt/asdf-install-wsl2#before-installing-asdf)
5. [Install asdf](https://github.com/Michelle-Lohwt/asdf-install-wsl2#install-wsl2)
6. [Add plugins](https://github.com/Michelle-Lohwt/asdf-install-wsl2#add-plugins)
7. [Install language](https://github.com/Michelle-Lohwt/asdf-install-wsl2#add-plugins)
8. [Install gems](https://github.com/Michelle-Lohwt/asdf-install-wsl2#install-gems)
9. [References](https://github.com/Michelle-Lohwt/asdf-install-wsl2#install-gems)

## What is WSL2
Read [Microsoft WSL2 Documentation](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

## What is asdf
Read [asdf virtual manager Documentation](http://asdf-vm.com/)

## Install WSL2
Video Reference: [WSL 2: Getting started](https://www.youtube.com/watch?v=_fntjriRe48&t=704s) (Watch from Overview until PowerShell Commands (0:00 - 8.23))

## Before installing asdf
1. In your Ubuntu, type `code .` to open up Visual Studio Code (VS Code)
2. Open your terminal in VS Code
3. In your terminal, it should be in already be Linux not Windows (You are in Windows if you have something like `PS C:\Users\>`), go to linux by typing `wsl`
```
$ PS C:\Users\>wsl

# Go to root directory
$ <user_name>: cd /
```
4. Do this to get dependencies for wsl2 (else you might got error: BUILD FAILED (Ubuntu 20.04 using ruby-build 20210804)) <br>
For more information related to solving this problem: read [here](https://discuss.rubyonrails.org/t/installing-rails-on-ubuntu-20-04-showing-build-failed-error/75642/4)
```
$ sudo apt-get update
$ sudo apt install autoconf bison build-essential libssl-dev libyaml-dev libreadline-dev zlib1g-dev libncurses-dev libffi-dev libgdbm-dev
```

## Install asdf
1. Follow the documentation
```
$ sudo apt install curl git
$ git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.8.1
```
2. Add `. $HOME/.asdf/asdf.sh` and `. $HOME/.asdf/completions/asdf.bash` in the end of `.bashrc` file
3. Call `code ~/.bashrc` in your terminal

Starting from here, we use these 2 videos as main references:
[Installing asdf and using it to install Go, Python & Terraform](https://www.youtube.com/watch?v=njM3-eejlho)
[Installing Ruby on Rails Using asdf](https://www.youtube.com/watch?v=Ji2jhj7t0bk&t=317s)

## Add plugins
```
$ asdf plugin add ruby
$ asdf plugin add nodejs
$ asdf plugin add yarn
```

## Install language
1. Install ruby, nodejs and yarn latest version (or you can specify the version needed)
```
$ asdf install ruby latest
$ asdf install nodejs latest
$ asdf install yarn latest
```
2. Check the version installed (the versions mentioned here is the latest version I downloaded)
```
$ asdf list
nodejs
  16.8.0
ruby
  3.0.2
yarn
  1.22.11
```
3. Add to your shell
```
$ asdf shell ruby 3.0.2
$ asdf shell nodejs 16.8.0
$ asdf shell yarn 1.22.11
```
4. Add to global
```
$ asdf global ruby 3.0.2
$ asdf global nodejs 16.8.0
$ asdf shell yarn 1.22.11
```

## Install gems
1. Check where is your ruby and gem
```
$ which ruby
/home/<user>/.asdf/shims/ruby

$ which gem
/home/<user>/.asdf/shims/gem
```
2. If not in `.asdf/shims`, do `asdf reshim ruby 3.0.2` (specify the version yourself, mine here is 3.0.2)
3. Install gems
```
$ gem install rails
```
4. The rest can follow [Installing Ruby on Rails Using asdf](https://www.youtube.com/watch?v=Ji2jhj7t0bk&t=317s) (starting 5:24)

## References
1. [Microsoft WSL2 Documentation](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
2. [asdf virtual manager Documentation](http://asdf-vm.com/)
3. [WSL 2: Getting started](https://www.youtube.com/watch?v=_fntjriRe48&t=704s)
4. [BUILD FAILED (Ubuntu 20.04 using ruby-build 20210804)](https://discuss.rubyonrails.org/t/installing-rails-on-ubuntu-20-04-showing-build-failed-error/75642/4)
5. [Installing asdf and using it to install Go, Python & Terraform](https://www.youtube.com/watch?v=njM3-eejlho)
6. [Installing Ruby on Rails Using asdf](https://www.youtube.com/watch?v=Ji2jhj7t0bk&t=317s)
