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


##### Bonus: Slack Darkmode!

Open Applications in Finder -> Cmmd Click -> Show Package Contents -> navigate to:`Resources\app.asar.unpacked\src\static\ssb-interop.js`

Paste this snippet at the bottom:

```
document.addEventListener('DOMContentLoaded', function() {
  $.ajax({
   url: 'https://raw.githubusercontent.com/laCour/slack-night-mode/master/css/raw/black.css',
   success: function(css) {
     $("<style>.c-message, .c-virtual_list__item { background: #222 !important; }</style>").appendTo('head')
     $("<style></style>").appendTo('head').html(css);
   }
 });
});
```

Sidebar Theme:

```
#222222,#111111,#111111,#66AADD,#555555,#EEEEEE,#66DD66,#DD666D
```

This may need to be re-added when Slack updates.

Consider:

- JAD
- AD1
- AD12
- Verizon
