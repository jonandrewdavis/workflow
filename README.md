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

---

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

### Exclude Node Modules from auto complete, to assist with TS, etc.

It says here that folder_exclude_patterns hides it from the side bar, while binary_file_patterns hides it from search. So if you want to exclude it from both, you can open the User Settings file (which overrides the default settings) and add;

```

{
    "folder_exclude_patterns": ["node_modules"],
    "binary_file_patterns": ["*/node_modules/*"]
}
```

### Notes for `No imports found for ...` message

Looks like you do not have opened folders in current Sublime window.

It is recommended to create project from your working files and folders, you can do it in top menu:
`Project -> Save project as...`
Save project file in any place you want.
Then restart Sublime.

Currently, it is not posssible to detect when project was switched (Project -> Quick Switch Project),
in this case you need manually re-initialize plugin:
Select `Import Helper: Initialize / Setup / Update modules` from command palette

### Oh My ZSH on Windows - WSL2 Alpine Instructions

From "scratch", a blank Windows installation.

We'll be getting:

- WSL2
- Alpine
- Windows Terminal
- ZSH

First, we'll need to get WSL2, turn it on, and update it.
We'll use the "manual" section of this guide. https://docs.microsoft.com/en-us/windows/wsl/install-win10

- Enable the WSL feature, starting a CMD prompt (right click and run as administrator to prevent permission issues):

```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

### Alpine Linux

The next few steps I found are required specifically for Alipine Linux. For this use case and many others, it's my go-to distro by virture of being super lightwieght. Read more here: https://alpinelinux.org/about/

You may also do this via the "Windows Feature" GUI, by searching and checking the box.

Next, we'll need to enable this this feature, as it is required for Alpine

```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

- Download and install the kernel update (again, required for Alpine)
  https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
- Restart your machine. I found out the hard way that this is the point where a restart seems to be required. It's also a good precaution to avoid errors.
- Open up CMD again:

```
wsl --set-default-version 2
```

- Go to the Windows Store and search: Alpine
- Install
- Launch, provide `Enter new UNIX username` and password, remember this password, we'll use it to gain root later.
- Go to the Windows Store, get the Windows Terminal
- Open it, click the arrow in the top menu, go to settings,
- Edit the JSON to use your new Alpine guid as the default
- Open Windows Terminal, you should have an Alpine env running, try `ls`
- We can't really do anything yet, since our user has no permissions, by intention! apk update, fails, You can't even sudo: sudo apk update
- "whoami"
- Let's follow: This excellent guide, https://docs.alpinelinux.org/user-handbook/0.1a/Working/post-install.html

```
adduser -h /home/alrund -s /bin/ash jon
```

Enter password, then:

```
su -l root
apk add sudo
echo '%wheel ALL=(ALL) ALL' > /etc/sudoers.d/wheel
adduser alrund wheel # put in your user name
```

- Start a new session to get out of root. Do "whoami"
- Time for ZSH and other essential packages. Alpine uses "apk" in this format:

```
sudo apk update
sudo apk add zsh
```

- Should go fast: OK: 17 MiB in 20 packages
- More

```
sudo apk add curl
sudo apk add git
sudo apk add openssh-keygen
sudo apk add openssh-client
sudo apk add zsh-vcs
```

- Now the fun part: Ohmyzsh and all the good stuff

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

- From here it should be identical to the guide, you'll need the zsh-vcs, and you may need to right click the font install and say "run in cmd"

```
prompt_context() {
  if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
    prompt_segment green black "%(!.%{%F{yellow}%}.)(╯°□°)╯︵ ┻━┻"
  fi
}

alias sublime='"/mnt/c/Program Files/Sublime Text 3/subl.exe"'

alias open='"explorer.exe"'
```

Neofetch

# ScratchPad

---

Setting up WSL2, Windows Terminal and oh-my-zsh `https://blog.nillsf.com/index.php/2020/02/17/setting-up-wsl2-windows-terminal-and-oh-my-zsh/`
Alternative guide: https://docs.microsoft.com/en-us/windows/wsl/install-win10

- Windows Feature
- Microsoft Store -> Alpine -> Install -> Launch
- Install, provide `Enter new UNIX username` and password.
- New Windows CMD window:

```
wsl -l -v
...
wsl --set-version Alpine 2
```

- If you get: "WSL 2 requires an update to its kernel component."
  Go here: https://aka.ms/wsl2kernel

```
Download the latest package:
    WSL2 Linux kernel update package for x64 machines
```

**_ IMPORTANT: Restart here _**

Sets Default:
wsl --set-default-version 2

Troubleshooting msgs from my CMD:

```
C:\Users\jonan>wsl --set-version Alpine 2
Conversion in progress, this may take a few minutes...
For information on key differences with WSL 2 please visit https://aka.ms/wsl2
Conversion complete.
```

```
Deployment Image Servicing and Management tool
Version: 10.0.19041.844

Image Version: 10.0.19042.867

Enabling feature(s)
[==========================100.0%==========================]
The operation completed successfully.

C:\Windows\system32>
```

Microsoft Docs for WSL `https://docs.microsoft.com/en-us/windows/wsl/install-win10`

Resource: `https://nickjanetakis.com/blog/using-wsl-and-mobaxterm-to-create-a-linux-dev-environment-on-windows#wsl-conemu-and-mobaxterm-to-the-rescue`

Tricky: make sure you get the users set up properly, and password protect root. Add the new user to the sudos.

Fix Agnoster error: `theme_precmd:1: vcs_info: function definition file not found`
`prompt_git:40: vcs_info: function definition file not found`

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
sudo apk add git
sudo apk add openssh-keygen
sudo apk add openssh-client

```

More

```
sudo apk add openssh-client
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

AWS was a pain, but using apk add worked

```
sudo apk update
sudo apk add aws-cli
```

#### Musings / Notes:

If only there was a way to get the windows key to act like Mac's command key, for switching tabs... would need to be CRTL for some things, ALT for ALT Tab.

Some ZSH Cheats
https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet

TO DO: Clean up all this WSL stuff and write a blog post about WSL
windows terminal, zsh, set up on machine, boot time tweaks and video of machine. O/C blog post?

### Construction of New Blog

Requirements:

- Static Site generator, taking posts from markdown to html/css/js
- Fast
- Easy build process
- New posts should be as easy as adding a .md
- Needs to include images
- MUST have syntax highlighting
- Host on S3/CloudFront
- Support a markdown format close to Github flavor, or use: https://commonmark.org/help/

Execution Options:

- Vercel
- Rust/Zola/Jekkyl??/Hyde theme
- Custom code/Create React App

Adding and testing a new SSH key

https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account

```

    CTRL + A — Move to the beginning of the line
    CTRL + E — Move to the end of the line
    CTRL + [left arrow] — Move one word backward (on some systems this is ALT + B)
    CTRL + [right arrow] — Move one word forward (on some systems this is ALT + F)
    CTRL + U — (bash) Clear the characters on the line before the current cursor position
    CTRL + U —(zsh) If you're using the zsh, this will clear the entire line
    CTRL + K — Clear the characters on the line after the current cursor position
    ESC + [backspace] — Delete the word in front of the cursor
    CTRL + W — Delete the word in front of the cursor
    ALT + D — Delete the word after the cursor
    CTRL + R — Search history
    CTRL + G — Escape from search mode
    CTRL + - — Undo the last change
    CTRL + L — Clear screen
    CTRL + S — Stop output to screen
    CTRL + Q — Re-enable screen output
    CTRL + C — Terminate/kill current foreground process
    CTRL + Z — Suspend/stop current foreground process
    !! — Execute last command in history
    !abc — Execute last command in history beginning with abc
    !abc:p — Print last command in history beginning with abc

```
