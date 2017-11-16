# NVM (Node Version Manager)

Install nvm --> [Install nvm with Homebrew to use multiple versions of node and iojs easily](http://dev.topheman.com/install-nvm-with-homebrew-to-use-multiple-versions-of-node-and-iojs-easily/)

    brew update
    brew install nvm
    mkdir ~/.nvm
    nano ~/.bash_profile

In your .bash_profile file (you may be using an other file, according to your shell), add the following :

    export NVM_DIR=~/.nvm
    source $(brew --prefix nvm)/nvm.sh

Back to your shell, activate nvm and check it (if you have other shells opened and you want to keep them, do the same) :

    source ~/.bash_profile
    echo $NVM_DIR

Now, you can install node :

    nvm install 0.12

From now on, you’re using the v0.12.x of node on this shell, you can install your global dependencies such as grunt-cli (they will be tied up to this version of node).

You may want to install other versions, just do :

    nvm install 0.10
    nvm install iojs
    ...

You’ll have to npm install -g your global dependencies for each version.

Switch of node version with nvm use 0.10 (more infos here).

To have a node activated by default (not to have to nvm use on each new shell), run this (stable being the id of the version):

    nvm alias default stable
~
Now, you can run multiple versions of node on your computer.
