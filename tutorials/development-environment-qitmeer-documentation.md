# Development Environment :: Qitmeer Documentation

This tutorial covers most qitmeer applications, including qitmeer, qitmeer-cli, qitmeer-miner, etc.

#### Shell and package manager <a href="#shell-and-package-manager" id="shell-and-package-manager"></a>

A uniform command style and a handy package manager will greatly increase efficiency.

**Windows**

Since windows commands are not in unix-like style, so it is strongly command to install Msys2, which presents a unix shell and a package manager (pacman). It would provide consistent experience as Mac or Ubuntu do.

* Download and install msys2 from [http://repo.msys2.org/distrib/x86\_64/msys2-x86\_64-20190524.exe](http://repo.msys2.org/distrib/x86\_64/msys2-x86\_64-20190524.exe)
* Find and run “MSYS2 MSYS” in Start Menu to MSYS2 shell
* Run following command to setup system environment variables

```
export PATH=/mingw64/bin:$PATH
export LD_LIBRARY_PATH=/mingw64/lib:$LD_LIBRARY_PATH

# update packages, it may ask you to re-open a terminal to process
# repeat this instruction until no packages to update
pacman -Syu

```

![Figure 2](https://qitmeer.github.io/docs/images/development-environment/msys2.png)

**Mac**

Mac is a Unix based OS, we just need to install the package manager.

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew update
brew upgrade
```

**Ubuntu**

Ubuntu has build-in package manager apt, just update to the latest state

```
sudo apt update
sudo apt upgrade
```

#### Install Requisite <a href="#install-requisite" id="install-requisite"></a>

Before install Qitmeer, we need install git and golang.

**Windows**

```
 pacman -S git mingw64/mingw-w64-x86_64-go
export GOROOT=/mingw64/lib/go
export GOPATH=/mingw64
```

**Mac**
