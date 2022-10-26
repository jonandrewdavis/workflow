# workflow 

Personal development set up guide

### Terminal

- Iterm2 
  - Load settings from .plist file
  - Default profile `.json` included, but may not be necessary
- Alacritty 
  - (Coming soon)

### Shell

- zsh
- Oh My Zsh
  - Copy `.zshrc` from this repo
  - Includes the theme [agnoster-zsh-theme](https://github.com/agnoster/agnoster-zsh-theme)
  - Install [Fira Code](https://github.com/tonsky/FiraCode) font
  - Install [Powerline](https://github.com/powerline/fonts) fonts patch
  - Install [Nerd Fonts](https://www.nerdfonts.com/font-downloads) - Fira Code Retina

### Text Editor

- [neovim](https://neovim.io/) 
- [AstroNvim](https://github.com/AstroNvim/AstroNvim)
- TODO: Set up [user config](https://astronvim.github.io/Configuration/manage_user_config) 
- TODO: LSP and TSP commands
- TODO: Themes? Perhaps [Catpuccino](https://github.com/catppuccin/nvim) 

```
TODO: Command for copying in init.lua
```


### Command Line Utilites:

- Homebrew (macOS)
- autojump
- git
- gh
- n
- aws-cli
- yarn
- [blackbox](https://github.com/StackExchange/blackbox) 
- [prettier](https://prettier.io/docs/en/install.html)
- rustup 
- vtop
- [speed-test](https://github.com/sindresorhus/speed-test)
- [ack](https://beyondgrep.com/)
- [caniuse-cmd](https://github.com/sgentle/caniuse-cmd)
- omz plugin: [websearch](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/web-search)
- omz `macos` plugin: `plugins=(... macos)`  
- omz `copyfile` plugin: [copyfile](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/copyfile)
- omz plugin: fancy-ctrl-z

### Other Essential Apps

- Slack
- Chrome
- Discord

### More macOS Apps

- Amethyst
- Things
- iA Writer

### Secrets

- (Adding a new SSH key to Github)[https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account]
- TODO: Add blackbox commands


### Shortcuts 

- omz git plugin [aliases](https://kapeli.com/cheat_sheets/Oh-My-Zsh_Git.docset/Contents/Resources/Documents/index)
- omz macOS plugin [shortcuts](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/macos)


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
