# workflow

A definitive guide to setting up a new work environment

### Terminal
- Iterm2 (MacOS)
  - Load settings from .plist file
  - Default profile `.json` included, but may not be necessary
- Guake (Linux)
  - Use settings file (Coming soon)

### Shell
- zsh
- Oh My Zsh
  - Copy `.zshrc` from this repo
  - Includes the theme [agnoster-zsh-theme](https://github.com/agnoster/agnoster-zsh-theme)
  - Install [Fira Code](https://github.com/tonsky/FiraCode) font
  - Install [Powerline](https://github.com/powerline/fonts) fonts patch

### Text Editor
- [Sublime Text](https://www.sublimetext.com/)
- Settings file from this repo
- Keybindings from this repo
- Install Package Control
- Package Control Settings
    - Remember to update proxy for Package Control
    - Should get required packages like JSPrettier
- Considering Fira Code here too
- Double check `subl .` binding in shell

### Command Line Utilites:
- Homebrew
- autojump
- git
- n
- aws-cli
- yarn

### Other Web Dev Considerations:

- ReasonML
- Elm
- Heroku
- Create React App
- More coming soon

### Other Essential Apps

- Slack
- Chrome

### More macOS Apps

- Amethyst
- Things

-----

### Snippets

- Coming Soon

### Startup for Linux:

Guake, xmodmap -c ./Xmodmap

```
in ~/
xmodmap -c .Xmodmap
```
```
redshift 3000:3000
```
```
https://wiki.archlinux.org/index.php/Libinput
```

### Oh My ZSH on Windows - WSL2 Alpine Instructions

Setting up WSL2, Windows Terminal and oh-my-zsh `https://blog.nillsf.com/index.php/2020/02/17/setting-up-wsl2-windows-terminal-and-oh-my-zsh/`

Microsoft Docs for WSL `https://docs.microsoft.com/en-us/windows/wsl/install-win10`

Resource:  `https://nickjanetakis.com/blog/using-wsl-and-mobaxterm-to-create-a-linux-dev-environment-on-windows#wsl-conemu-and-mobaxterm-to-the-rescue`

Tricky: make sure you get the users set up properly, and password protect root. Add the new user to the sudos.

Fix Agnoster error: `theme_precmd:1: vcs_info: function definition file not found`
```
apk add zsh-vcs
```

Open to the folder in windows
```
explorer.exe .
```

Git and other apks
```
sudo apk add
```
these, amoung others:
```
git
openssh-keygen
```
More
```
sudo apk --update add openssh-client
```

Sublime Shortcut and Command line fun for windows
```
# User configuration

cd ~

prompt_context() {
  if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
    prompt_segment green black "%(!.%{%F{yellow}%}.)(╯°□°)╯︵ ┻━┻"
  fi
}

alias sublime='"/mnt/c/Program Files/Sublime Text 3/subl.exe"'


```

#### Musings / Notes: 

If only there was a way to get the windows key to act like Mac's command key, for switching tabs... would need to be CRTL for some things, ALT for ALT Tab.

Some ZSH Cheats
https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet



TO DO: Clean up all this WSL stuff.