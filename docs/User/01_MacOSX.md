# Bootstrapping on Mac OS
Here's how to get the steward running on Mac OS X 10.8 (Mountain Lion).

First, make sure that _/usr/local/bin_ is before _/usr/bin_ in your $PATH.

Second, make sure you have _Xcode_ installed on your system,
and after starting _Xcode_ go to the "Preferences/Downloads" window and install the _Command Line Tools_.

Second, get [homebrew](http://mxcl.github.io/homebrew/) on the system:

    $ ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
    $ brew doctor

If homebrew suggests anything, e.g.,

    brew install git
    brew upgrade git

    ...and so on...

please do so. Keep doing this until you get

    brew doctor
    Your system is ready to brew.

Then install the USB compatibility library

    brew install libusb-compat

Then, put the [node version manager (nvm)](https://github.com/creationix/nvm) on the system:

    git clone git://github.com/creationix/nvm.git ~/.nvm
    echo ". ~/.nvm/nvm.sh" >> ~/.bashrc  
    . ~/.nvm/nvm.sh

Then install the v0.10.12 release of [_node.js_](http://nodejs.org) on the system:

    nvm install v0.10.12
    nvm alias default v0.10.12

(This isn't the most current version, but all the dependencies work with it...)

Then go to the _steward_ directory and install the libraries:

    cd steward/steward
    npm install -l

Note that the top-level directory may be called _steward-master_, in that case you want to:

    cd steward-master/steward
    npm install -l

instead.

### Alternative method to install Node.js

_The nvm system is based around the bash shell. If you run tcsh or another alternative, it's not going to work for you. You'll have to install node by hand. Go ahead and checkout Node.js from the Github repository,_

    git clone https://github.com/joyent/node.git

_change directory and switch to v0.10.12 release._

    cd node
    git checkout v0.10.12 -b v0.10.12

_Now go ahead and build,_

    ./configure
    make
    sudo make install

_before proceeding as normal._

### If you have problems building the steward

_If you have problems at the npm install stage when building the steward, you should clean up your environment and try again,_

    rm -rf node_modules
    npm cache clean
    rm -rf ~/.npm/_git-remotes
    git pull upstream master

And if that fails, also try:

    rm -rf ~/.node-gyp
    rm -rf ~/.npm
    rm -rf ~/.nvm
    rm -rf ~/.npmrc

and then go back to the

    npm install -l

## Instructions for starting the steward

The _run.sh_ script does three things:

* The script changes the group/permissions for _/dev/bpf*_ and flushes the arp caches.
The steward runs libpcap in order to examine arp traffic.
On most systems, the Berkeley Packet Filter (bpf) is used by [libpcap](http://www.tcpdump.org)
in order to capture network traffic.
In turn, _libpcap_ reads from devices named _/dev/bpf*_ - so these files need to be readable by the steward.
The _run.sh_ script assumes that the steward is running under group _admin_, so that's what it changes the group to.

* The script reads the _nvm_ initialization script in order to set the environment for _node.js_.

* The script runs the _node_ program on the _index.js_ file and the steward begins.

You will probably want to customize this script for yourself.

When the script starts, it will bring a lot of stuff on the console.
Over time, the verbosity will decrease, but for now, it should give comfort...

## If you have build failures
You may want to do a "hard reset" on your _node.js_ installation:

    rm -rf ~/.node-gyp ~/.npm ~/.nvm ~/.npmrc

and then start again by installing _nvm_.
