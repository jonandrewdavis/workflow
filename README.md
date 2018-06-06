# workflow

Guake || Iterm2
	- Update keybindings
- zsh
- Oh My ZSH
- top-programming-fonts
- Powerline font
- agnoster theme

### Text Editor
- Sublime Text 3
- Package Control
	- Prettier
- Preferences 
	- Hot-exit: true
	- Tab Size: 2
	- See Below for config file

### JS tooling
- n
- node
- yarn

### Programming

- Haskell - GHC
- Python
- ReasonML
- Elm

### Web

- git
- AWS cli 	


-----

## Snippets



sudo apt install curl

sudo apt-get install zsh

sudo apt-get install git2



curl -L https://github.com/hbin/top-programming-fonts/raw/master/install.sh | bash



Sublime: 

https://www.sublimetext.com/docs/3/linux_repositories.html

wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
sudo apt-get update
sudo apt-get install sublime-text


ZSH

sudo apt-get install fonts-powerline

sudo apt install guake




sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

set guake 


apt-get install ghc
apt-get install libx11-dev





WM 

 ubu@ububox  ~  wmctrl -m
Name: Xfwm4
Class: xfwm4
PID: 747
Window manager's "showing the desktop" mode: N/A
 ubu@ububox  ~  




```
{
	"binary_file_patterns":
	[
		"*.css.map",
		"*.min.js",
		"*.jpg",
		"*.jpeg",
		"*.png",
		"*.gif",
		"*.ttf",
		"*.tga",
		"*.dds",
		"*.ico",
		"*.eot",
		"*.pdf",
		"*.swf",
		"*.jar",
		"*.zip",
		".svg"
	],
	"create_window_at_startup": false,
	"default_tab_size": 2,
	"ensure_newline_at_eof_on_save": true,
	"file_exclude_patterns":
	[
		"*.DS_Store",
		"*.css.map",
		"*.min.js",
		"*.js.map",
		"*.bundle.js",
		"yarn.lock",
		"bundle-analyzer-*"
	],
	"folder_exclude_patterns":
	[
		".git",
		"node_modules",
		"rethinkdb_data",
		"public/build",
		"run/build",
		"build",
		"coverage",
		"__snapshots__",
		"logs",
		"testresults"
	],
	"font_size": 21,
	"hot_exit": false,
	"ignore_vcs_packages": true,
	"ignored_packages":
	[
		"Vintage"
	],
	"remember_open_files": false,
	"tab_size": 2,
	"translate_tabs_to_spaces": true,
	"trim_trailing_white_space_on_save": true
}
```


