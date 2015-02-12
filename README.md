## Adjusting your shell

The shell program /bin/bash (hereafter referred to as just "the shell") uses a collection of startup files to help create an environment. Each file has a specific use and may affect login and interactive environments differently. The files in the /etc directory generally provide global settings. If an equivalent file exists in your home directory it may override the global settings.

This project defines a simple etc directory you can clone to your home directory. It comes with some basic configurations like displaying current git branches and status and basic colors.

## How this project is organized

#### Aliases

The `bash_aliases.sh` is where you can define aliases for commands you use all the time. For example, I personally prefer my `ls` command to show also hidden files, for that I added a alias that overrides the default `ls` to always be `ls -la`. Usually I also have aliases for all the projects I'm currently working.

#### Variables

The `bash_variables.sh` is the place where you can define variables for you environment like `EDITOR="subl -w"` sets sublime as the default editor. It's also a good place to keep your PATH variable, which is the default place where your shell will look for commands.

#### Prompt

The `bash_prompt.sh` has a collection of possible colors declared and the last line (`PS1=...`) is the place where you can customize your prompt. By assigning values to PS1 you are overriding the default way to display your prompt in bash.

The last line also uses the `__git_ps1` variable. This variable is created in `git-prompt.sh`, which offers some nice extra features for our prompt, like ability to display what is your current branch in git or if you last changes are staged or not for commit.

## How to use

First clone this repo into your home directory using the following commands (or fork it and clone from your own account):

`
cd ~
git clone git@github.com:starterleague/dotfiles.git etc
`

First thing you should do is to backup your original .bashrc and .bash_profile. You can do that running:

`
cp ~/.bashrc ~/.bashrc_bkp
cp ~/.bash_profile ~/.bash_profile_bkp
`

*PS.: Not everybody has a .bash_profile*

The next step is to open your .bashrc and add the following line as the last line in the file:

`
source ~/etc/bashrc
`

OPTIONAL: If you feel comfortable you could copy all the possible variables inside your current .bash_rc to the ~/etc/bash_variables.sh.

## Keeping your changes versioned

This project is more like a boilerplate to start customizing your terminal based on your preferences. It is always nice to keep your things online and safe so I highly recommend forking this repo to your own github account and every change you make you can push to your own fork. By doing that you make sure you can setup a new machine with all your personal preferences pretty fast.