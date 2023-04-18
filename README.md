# homebrew-no-sudo
How to install Homebrew &amp; node without sudo privilege 

## Step 1: Install Homebrew without sudo:
`
mkdir homebrew && curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew
`

## Step 2: Edit the file path to inclue homebrew
`
echo "# Homebrew\nexport PATH=$HOME/homebrew/bin:\$PATH" >> .zshrc
`
`
source ~/.zshrc
`
or just run 
`
export PATH=$HOME/homebrew/bin:$PATH
`
## Step 3: install nvm with brew
`
brew update
`
`
brew install nvm
`
`
mkdir ~/.nvm
`
`
echo "export NVM_DIR=~/.nvm\nsource \$(brew --prefix nvm)/nvm.sh" >> .zshrc
`
`
source ~/.zshrc
`
## Step 4: config nvm in the zshrc file 

open zshrc file with nano and edit:
`
nano ~/.zshrc
`
paste this command at the end of the file:
`
source ~/.nvm/nvm.sh
`
enter CTRL + X to save and exit nano 

Then both brew and nvm are good to go!

Use nvm to install node & npm instead of Homebrew, as the prefix of homebrew is not /usr/local/, and it might fail to install some packages which require the prefix of homebrew should be usr/local.

## Reference:
- [How to install nvm with brew](https://medium.com/devops-techable/how-to-install-nvm-node-version-manager-on-macos-with-homebrew-1bc10626181)
- [Homebrew official documentation](https://docs.brew.sh/Installation#untar-anywhere-unsupported)
- [Install Homebrew without sudo](https://www.scivision.dev/macos-homebrew-non-sudo)
- [How to install Homebrew without sudo](https://superuser.com/questions/619498/can-i-install-homebrew-without-sudo-privileges)
- [Solution of nvm not found error](https://stackoverflow.com/questions/16904658/node-version-manager-install-nvm-command-not-found)
- [Create & Edit zshrc file on Mac](https://superuser.com/questions/886132/where-is-the-zshrc-file-on-mac)
- [Github Issue: Debug Homebrew prefix warning](https://github.com/Homebrew/install/issues/121)



