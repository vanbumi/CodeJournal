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

<br>

## More about nvm

Get help:

	dyo-mac:~ dyo-medio$ nvm --help

Node Version Manager

Note: <version> refers to any version-like string nvm understands. This includes:
 
- full or partial version numbers, starting with an optional "v" (0.10, v0.1.2, v1)
- default (built-in) aliases: node, stable, unstable, iojs, system
- custom aliases you define with `nvm alias foo`

 Any options that produce colorized output should respect the `--no-colors` option.

Usage:

	nvm --help                                Show this message
	nvm --version                             Print out the installed version of nvm
 	
	nvm install [-s] <version>                Download and install a <version>, [-s] from source. Uses .nvmrc if available
    
		--reinstall-packages-from=<version>     When installing, reinstall packages installed in <node|iojs|node version number>
    
		--lts                                   When installing, only select from LTS (long-term support) versions
    
		--lts=<LTS name>                        When installing, only select from versions for a specific LTS line
    
		--skip-default-packages                 When installing, skip the default-packages file if it exists
    
		--latest-npm                            After installing, attempt to upgrade to the latest working npm on the given node version
  
		nvm uninstall <version>                   Uninstall a version
  
		nvm uninstall --lts                       Uninstall using automatic LTS (long-term support) alias `lts/*`, if available.
  
		nvm uninstall --lts=<LTS name>            Uninstall using automatic alias for provided LTS line, if available.
  
		nvm use [--silent] <version>              Modify PATH to use <version>. Uses .nvmrc if available
    
		--lts                                   Uses automatic LTS (long-term support) alias `lts/*`, if available.
    
		--lts=<LTS name>                        Uses automatic alias for provided LTS line, if available.
  
		nvm exec [--silent] <version> [<command>] Run <command> on <version>. Uses .nvmrc if available
    
		--lts                                   Uses automatic LTS (long-term support) alias `lts/*`, if available.
    
		--lts=<LTS name>                        Uses automatic alias for provided LTS line, if available.
  
		nvm run [--silent] <version> [<args>]     Run `node` on <version> with <args> as arguments. Uses .nvmrc if available
    
		--lts                                   Uses automatic LTS (long-term support) alias `lts/*`, if available.
    
		--lts=<LTS name>                        Uses automatic alias for provided LTS line, if available.
		
		nvm current                               Display currently activated version
		
		nvm ls                                    List installed versions
  	
		nvm ls <version>                          List versions matching a given <version>
  	
		nvm ls-remote                             List remote 
		versions available for install
    
		--lts                                   When listing, only 
		show LTS (long-term support) versions
  	nvm ls-remote <version>                   List remote versions available for install, matching a given <version>
    
		--lts                                   When listing, only show LTS (long-term support) versions
    
		--lts=<LTS name>                        When listing, only show versions for a specific LTS line
  	
		nvm version <version>                     Resolve the given description to a single local version
  
		nvm version-remote <version>              Resolve the given description to a single remote version
    
		--lts                                   When listing, only select from LTS (long-term support) versions
    
		--lts=<LTS name>                        When listing, only select from versions for a specific LTS line
 
 		nvm deactivate                            Undo effects of `nvm` on current shell
  	
		nvm alias [<pattern>]                     Show all aliases beginning with <pattern>
  
		nvm alias <name> <version>                Set an alias named <name> pointing to <version>
  
		nvm unalias <name>                        Deletes the alias named <name>
  
		nvm install-latest-npm                    Attempt to upgrade to the latest working `npm` on the current node version
  
		nvm reinstall-packages <version>          Reinstall global `npm` packages contained in <version> to current version
  
		nvm unload                                Unload `nvm` from shell
  	
		nvm which [<version>]                     Display path to installed node version. Uses .nvmrc if available
  
		nvm cache dir                             Display path to the cache directory for nvm
  
		nvm cache clear                           Empty cache directory for nvm

Example:

	nvm install 8.0.0                     Install a specific version number
  
	nvm use 8.0                           Use the latest available 8.0.x release
  
	nvm run 6.10.3 app.js                 Run app.js using node 6.10.3
  
	nvm exec 4.8.3 node app.js            Run `node app.js` with the PATH pointing to node 4.8.3
  
	nvm alias default 8.1.0               Set default node version on a shell
  
	nvm alias default node                Always default to the latest available node version on a shell

Note:
  
	to remove, delete, or uninstall nvm - just remove the `$NVM_DIR` folder (usually `~/.nvm`)