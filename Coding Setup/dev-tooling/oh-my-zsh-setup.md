# Oh My Zsh Setup Guide

A comprehensive guide to setting up and customizing Oh My Zsh for enhanced terminal productivity, including themes, plugins, and essential commands.

## Overview

Oh My Zsh is a framework for managing your Zsh configuration, making your terminal more powerful and easier to use with themes, plugins, and aliases.

## Installation

### Prerequisites
- macOS, Linux, or Windows with WSL
- Zsh shell (usually pre-installed on macOS and Linux)

### Step 1: Install Oh My Zsh
```bash
# Install Oh My Zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Or using wget
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Step 2: Verify Installation
```bash
# Check if Oh My Zsh is installed
echo $ZSH

# Check Zsh version
zsh --version

# Restart terminal or reload configuration
source ~/.zshrc
```

### Step 3: Set Zsh as Default Shell
```bash
# Check current shell
echo $SHELL

# Change default shell to Zsh
chsh -s $(which zsh)

# Log out and log back in, or restart terminal
```

## Configuration

### Basic Configuration

#### .zshrc File
```bash
# Path to your Oh My Zsh installation
export ZSH="$HOME/.oh-my-zsh"

# Theme setting
ZSH_THEME="robbyrussell"

# Plugin configuration
plugins=(git docker npm node)

# Load Oh My Zsh
source $ZSH/oh-my-zsh.sh

# User configuration
export PATH=$HOME/bin:/usr/local/bin:$PATH

# Aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
```

#### Environment Variables
```bash
# Add to ~/.zshrc
export EDITOR="code"  # VS Code
export VISUAL="code"
export BROWSER="open"  # macOS
export LANG="en_US.UTF-8"
export LC_ALL="en_US.UTF-8"

# Development paths
export PATH="/usr/local/bin:$PATH"
export PATH="$HOME/.local/bin:$PATH"
export PATH="$HOME/.npm-global/bin:$PATH"
```

## Popular Themes

### Built-in Themes

#### Robby Russell (Default)
```bash
ZSH_THEME="robbyrussell"
```

#### Agnoster
```bash
ZSH_THEME="agnoster"
```

#### Powerlevel10k (External)
```bash
# Install Powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

# Set theme
ZSH_THEME="powerlevel10k/powerlevel10k"
```

#### Dracula
```bash
# Install Dracula theme
git clone https://github.com/dracula/zsh.git $ZSH_CUSTOM/themes/dracula

# Set theme
ZSH_THEME="dracula"
```

### Custom Theme Configuration
```bash
# Customize prompt
PROMPT='%{$fg[red]%}%n%{$reset_color%}@%{$fg[blue]%}%m %{$fg[yellow]%}%~ %{$reset_color%}%% '

# Add git information
autoload -Uz vcs_info
precmd() { vcs_info }
zstyle ':vcs_info:git:*' formats '(%b)'
setopt PROMPT_SUBST
PROMPT='%n@%m %~ ${vcs_info_msg_0_}%% '
```

## Essential Plugins

### Git Plugin
```bash
# Add to plugins array
plugins=(git)

# Git aliases (automatically provided)
alias gst='git status'
alias ga='git add'
alias gc='git commit'
alias gp='git push'
alias gl='git pull'
alias gco='git checkout'
alias gcb='git checkout -b'
alias gcm='git checkout main'
alias gb='git branch'
alias gba='git branch -a'
alias gbd='git branch -d'
alias gbD='git branch -D'
alias glog='git log --oneline --graph'
```

### Docker Plugin
```bash
# Add to plugins array
plugins=(git docker)

# Docker aliases
alias d='docker'
alias dc='docker-compose'
alias dps='docker ps'
alias dpsa='docker ps -a'
alias di='docker images'
alias dex='docker exec -it'
alias dlog='docker logs'
alias dlogf='docker logs -f'
```

### Node.js Plugin
```bash
# Add to plugins array
plugins=(git docker node)

# Node.js aliases
alias n='node'
alias ni='npm install'
alias nid='npm install --save-dev'
alias nig='npm install -g'
alias nr='npm run'
alias nrb='npm run build'
alias nrd='npm run dev'
alias nrt='npm run test'
alias nrs='npm run start'
```

### Python Plugin
```bash
# Add to plugins array
plugins=(git docker node python)

# Python aliases
alias py='python'
alias py3='python3'
alias pip='pip3'
alias pipi='pip install'
alias pipu='pip uninstall'
alias pipf='pip freeze'
alias pipr='pip install -r requirements.txt'
```

### Additional Useful Plugins
```bash
plugins=(
  git
  docker
  node
  python
  zsh-autosuggestions
  zsh-syntax-highlighting
  history
  extract
  web-search
  copypath
  dirhistory
  jsontools
)
```

## Custom Aliases

### System Aliases
```bash
# File operations
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
alias lt='ls -laht'
alias lsd='ls -la | grep "^d"'

# Directory navigation
alias ..='cd ..'
alias ...='cd ../..'
alias ....='cd ../../..'
alias .....='cd ../../../..'

# File editing
alias zshrc='code ~/.zshrc'
alias zshrcs='source ~/.zshrc'
alias bashrc='code ~/.bashrc'
alias vimrc='code ~/.vimrc'

# System utilities
alias c='clear'
alias h='history'
alias j='jobs -l'
alias path='echo -e ${PATH//:/\\n}'
alias ports='netstat -tulanp'
alias myip='curl http://ipecho.net/plain; echo'
alias weather='curl wttr.in'
```

### Development Aliases
```bash
# Git shortcuts
alias gs='git status'
alias ga='git add'
alias gc='git commit -m'
alias gp='git push'
alias gl='git pull'
alias gco='git checkout'
alias gcb='git checkout -b'
alias gcm='git checkout main'
alias gb='git branch'
alias gba='git branch -a'
alias gbd='git branch -d'
alias gbD='git branch -D'
alias glog='git log --oneline --graph --all'
alias gdiff='git diff'
alias gstash='git stash'
alias gpop='git stash pop'

# NPM shortcuts
alias ni='npm install'
alias nid='npm install --save-dev'
alias nig='npm install -g'
alias nr='npm run'
alias nrb='npm run build'
alias nrd='npm run dev'
alias nrt='npm run test'
alias nrs='npm run start'
alias nrl='npm run lint'
alias nrf='npm run format'

# Docker shortcuts
alias d='docker'
alias dc='docker-compose'
alias dps='docker ps'
alias dpsa='docker ps -a'
alias di='docker images'
alias dex='docker exec -it'
alias dlog='docker logs'
alias dlogf='docker logs -f'
alias dst='docker stop'
alias drm='docker rm'
alias drmi='docker rmi'
alias dprune='docker system prune -a'

# Python shortcuts
alias py='python'
alias py3='python3'
alias pip='pip3'
alias pipi='pip install'
alias pipu='pip uninstall'
alias pipf='pip freeze'
alias pipr='pip install -r requirements.txt'
alias venv='python -m venv'
alias activate='source venv/bin/activate'
```

## Functions

### Useful Functions
```bash
# Create directory and navigate to it
mkcd() {
  mkdir -p "$1" && cd "$1"
}

# Extract any archive
extract() {
  if [ -f $1 ] ; then
    case $1 in
      *.tar.bz2)   tar xjf $1     ;;
      *.tar.gz)    tar xzf $1     ;;
      *.bz2)       bunzip2 $1     ;;
      *.rar)       unrar e $1     ;;
      *.gz)        gunzip $1      ;;
      *.tar)       tar xf $1      ;;
      *.tbz2)      tar xjf $1     ;;
      *.tgz)       tar xzf $1     ;;
      *.zip)       unzip $1       ;;
      *.Z)         uncompress $1  ;;
      *.7z)        7z x $1        ;;
      *)     echo "'$1' cannot be extracted via extract()" ;;
    esac
  else
    echo "'$1' is not a valid file"
  fi
}

# Search in files
search() {
  grep -r "$1" .
}

# Find and replace in files
replace() {
  find . -type f -name "*.js" -exec sed -i "s/$1/$2/g" {} \;
}

# Create backup of a file
backup() {
  cp "$1" "$1.backup.$(date +%Y%m%d_%H%M%S)"
}

# Show directory size
ds() {
  du -sh "$1" 2>/dev/null | sort -hr
}

# Quick server
serve() {
  python3 -m http.server ${1:-8000}
}
```

## Advanced Configuration

### History Configuration
```bash
# History settings
HISTFILE=~/.zsh_history
HISTSIZE=10000
SAVEHIST=10000
setopt SHARE_HISTORY
setopt HIST_IGNORE_ALL_DUPS
setopt HIST_IGNORE_SPACE
setopt HIST_VERIFY
setopt HIST_REDUCE_BLANKS
setopt HIST_SAVE_NO_DUPS
setopt HIST_EXPIRE_DUPS_FIRST
setopt HIST_FIND_NO_DUPS
```

### Completion Configuration
```bash
# Enable completion
autoload -Uz compinit
compinit

# Completion settings
zstyle ':completion:*' auto-description 'specify: %d'
zstyle ':completion:*' completer _expand _complete _correct _approximate
zstyle ':completion:*' format 'Completing %d'
zstyle ':completion:*' group-name ''
zstyle ':completion:*' menu select=2
zstyle ':completion:*:default' list-colors ${(s.:.)LS_COLORS}
zstyle ':completion:*' list-colors ''
zstyle ':completion:*' list-prompt %SAt %p: Hit TAB for more, or the character to insert%s
zstyle ':completion:*' matcher-list '' 'm:{a-z}={A-Z}' 'm:{a-zA-Z}={A-Za-z}' 'r:|[._-]=* r:|=* l:|=*'
zstyle ':completion:*' select-prompt %SScrolling active: current selection at %p%s
zstyle ':completion:*' use-compctl false
zstyle ':completion:*' verbose true
```

### Key Bindings
```bash
# Key bindings
bindkey '^[[A' history-substring-search-up
bindkey '^[[B' history-substring-search-down
bindkey '^[[1;5C' forward-word
bindkey '^[[1;5D' backward-word
bindkey '^H' backward-kill-word
bindkey '^[[3~' delete-char
bindkey '^[[Z' reverse-menu-complete
```

## External Plugins

### zsh-autosuggestions
```bash
# Install zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# Add to plugins array
plugins=(git zsh-autosuggestions)
```

### zsh-syntax-highlighting
```bash
# Install zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Add to plugins array (must be last)
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

### fzf (Fuzzy Finder)
```bash
# Install fzf
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install

# Add to .zshrc
export FZF_DEFAULT_OPTS='--height 40% --layout=reverse --border'
export FZF_DEFAULT_COMMAND='fd --type f'
export FZF_CTRL_T_COMMAND='fd --type f'
export FZF_ALT_C_COMMAND='fd --type d'
```

## Troubleshooting

### Common Issues

#### Plugin Not Working
```bash
# Check if plugin is loaded
echo $plugins

# Reload configuration
source ~/.zshrc

# Check plugin directory
ls ~/.oh-my-zsh/plugins/
```

#### Theme Not Loading
```bash
# Check theme name
ls ~/.oh-my-zsh/themes/

# Set theme correctly
ZSH_THEME="theme-name"

# Reload configuration
source ~/.zshrc
```

#### Performance Issues
```bash
# Profile Zsh startup time
time zsh -i -c exit

# Disable plugins temporarily
plugins=()

# Check for slow plugins
for plugin in $plugins; do
  time source ~/.oh-my-zsh/plugins/$plugin/$plugin.plugin.zsh
done
```

### Performance Optimization
```bash
# Lazy load plugins
function load_plugin() {
  source ~/.oh-my-zsh/plugins/$1/$1.plugin.zsh
}

# Load plugins only when needed
alias docker='load_plugin docker && docker'
alias npm='load_plugin node && npm'
```

## Resources

### Documentation
- [Oh My Zsh Wiki](https://github.com/ohmyzsh/ohmyzsh/wiki)
- [Zsh Documentation](https://zsh.sourceforge.io/Doc/)
- [Oh My Zsh Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

### Community
- [Oh My Zsh GitHub](https://github.com/ohmyzsh/ohmyzsh)
- [Zsh Users](https://www.zsh.org/)
- [Reddit r/zsh](https://reddit.com/r/zsh)

### Additional Tools
- [Powerlevel10k](https://github.com/romkatv/powerlevel10k)
- [fzf](https://github.com/junegunn/fzf)
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)

---

*Last Updated: July 27, 2025* 