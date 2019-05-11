# ZPLUG
# Check if zplug is installed
if [[ ! -d ~/.zplug ]]; then
  git clone https://github.com/zplug/zplug ~/.zplug
  source ~/.zplug/init.zsh && zplug update --self
fi

# Essential
source ~/.zplug/init.zsh

zplug "robbyrussell/oh-my-zsh", use:"lib/*.zsh", defer:0
zplug "plugins/brew",   from:oh-my-zsh
zplug "plugins/bundler",   from:oh-my-zsh
zplug "plugins/cp",   from:oh-my-zsh
zplug "plugins/dnf",   from:oh-my-zsh
zplug "plugins/docker",   from:oh-my-zsh
zplug "plugins/docker-compose",   from:oh-my-zsh
zplug "plugins/gem",   from:oh-my-zsh
zplug "plugins/git",   from:oh-my-zsh, defer:3
zplug "plugins/golang",   from:oh-my-zsh, defer:3
zplug "plugins/gpg-agent",   from:oh-my-zsh
zplug "plugins/history",   from:oh-my-zsh, defer:3
zplug "plugins/httpie",   from:oh-my-zsh, defer:3
zplug "plugins/mvn",   from:oh-my-zsh
zplug "lukechilds/zsh-nvm"
zplug "lukechilds/zsh-better-npm-completion", defer:3
zplug "plugins/node",   from:oh-my-zsh
zplug "plugins/npm",   from:oh-my-zsh
zplug "plugins/rake",   from:oh-my-zsh
zplug "plugins/rsync",   from:oh-my-zsh
zplug "plugins/ruby",   from:oh-my-zsh
zplug "plugins/shrink-path",   from:oh-my-zsh
zplug "plugins/ssh-agent",   from:oh-my-zsh
zplug "plugins/systemd",   from:oh-my-zsh
zplug "plugins/tmux",   from:oh-my-zsh, defer:3
zplug "plugins/kubectl",   from:oh-my-zsh, defer:3
zplug "plugins/vagrant",   from:oh-my-zsh
zplug "plugins/z",   from:oh-my-zsh
zplug "plugins/zsh_reload",   from:oh-my-zsh
zplug "k4rthik/git-cal", as:command
zplug "michaeldfallen/git-radar", as:command, use:git-radar
zplug "ndbroadbent/scm_breeze", hook-build:"$ZPLUG_HOME/repos/ndbroadbent/scm_breeze/install.sh"
zplug "djui/alias-tips"
zplug "supercrabtree/k"
zplug "chriskempson/base16-shell", use:"base16-3024.dark.sh"
zplug "zsh-users/zsh-completions", use:src
zplug "zsh-users/zsh-autosuggestions", defer:3
zplug "zsh-users/zsh-syntax-highlighting", defer:3
zplug "zsh-users/zsh-history-substring-search", defer:3
zplug "knu/zsh-manydots-magic"
zplug "mafredri/zsh-async"
zplug "so-fancy/diff-so-fancy", as:command
zplug "Masterminds/glide", as:command, from:gh-r, use:"*linux*amd64*", rename-to:glide
zplug "jimmidyson/07b69911f783e3afd8cd4c8f8358c8f6", from:gist, defer:3
zplug "openshift/source-to-image", \
  as:command, \
  from:gh-r, \
  use:"*linux*amd64*", \
  rename-to:s2i

if ! zplug check --verbose; then
    printf "Install? [y/N]: "
    if read -q; then
        echo; zplug install
    fi
fi

zplug load

export TERM="xterm-256color"
export ZSH="/home/david/.oh-my-zsh"

ZSH_THEME="powerlevel9k/powerlevel9k"
POWERLEVEL9K_MODE='nerdfont-complete'

# Add kubernetes version
POWERLEVEL9K_CUSTOM_KUBERNETES_CONTEXT='kubernetes_context'
POWERLEVEL9K_CUSTOM_KUBERNETES_CONTEXT_BACKGROUND='blue'
POWERLEVEL9K_CUSTOM_KUBERNETES_CONTEXT_FOREGROUND='white'

kubernetes_context(){
    local k8s_context=$(kubectl config current-context)
    if [ -n "$k8s_context" ]; then
      echo -n "%$\U2388 $k8s_context% "
    fi
}

POWERLEVEL9K_CONTEXT_TEMPLATE='%n'
POWERLEVEL9K_CONTEXT_DEFAULT_FOREGROUND='white'
POWERLEVEL9K_BATTERY_LEVEL_BACKGROUND=(red3 darkorange3 darkgoldenrod gold3 yellow3 chartreuse2 mediumspringgreen green3 green3 green4 darkgreen)
POWERLEVEL9K_BATTERY_CHARGING="red"
POWERLEVEL9K_BATTERY_CHARGED="black"
POWERLEVEL9K_BATTERY_DISCONNECTED="black"

POWERLEVEL9K_MULTILINE_FIRST_PROMPT_PREFIX=''

POWERLEVEL9K_PROMPT_ON_NEWLINE=true
POWERLEVEL9K_MULTILINE_LAST_PROMPT_PREFIX="%F{014}\u2570%F{cyan}\uF460%F{073}\uF460%F{109}\uF460%f "
POWERLEVEL9K_VCS_MODIFIED_BACKGROUND='yellow'
POWERLEVEL9K_VCS_UNTRACKED_BACKGROUND='yellow'
POWERLEVEL9K_VCS_UNTRACKED_ICON='?'
POWERLEVEL9K_SHORTEN_DIR_LENGTH=2
POWERLEVEL9K_TIME_FORMAT="%D{%H:%M:%S %d/%m/%y}"
POWERLEVEL9K_TIME_BACKGROUND='white'
POWERLEVEL9K_RAM_BACKGROUND='yellow'
POWERLEVEL9K_LOAD_CRITICAL_BACKGROUND="white"
POWERLEVEL9K_LOAD_WARNING_BACKGROUND="white"
POWERLEVEL9K_LOAD_NORMAL_BACKGROUND="white"
POWERLEVEL9K_LOAD_CRITICAL_FOREGROUND="red"
POWERLEVEL9K_LOAD_WARNING_FOREGROUND="yellow"
POWERLEVEL9K_LOAD_NORMAL_FOREGROUND="black"
POWERLEVEL9K_LOAD_CRITICAL_VISUAL_IDENTIFIER_COLOR="red"
POWERLEVEL9K_LOAD_WARNING_VISUAL_IDENTIFIER_COLOR="yellow"
POWERLEVEL9K_LOAD_NORMAL_VISUAL_IDENTIFIER_COLOR="green"
POWERLEVEL9K_STATUS_VERBOSE=true
POWERLEVEL9K_STATUS_CROSS=true

POWERLEVEL9K_CONTEXT_ROOT_BACKGROUND="yellow"
POWERLEVEL9K_CONTEXT_ROOT_FOREGROUND="black"
POWERLEVEL9K_CONTEXT_SUDO_BACKGROUND="yellow"
POWERLEVEL9K_CONTEXT_SUDO_BACKGROUND="black"
POWERLEVEL9K_CONTEXT_REMOTE_BACKGROUND="orange"
POWERLEVEL9K_CONTEXT_SUDO_BACKGROUND="red"

POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(context custom_kubernetes_context battery dir vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(status dir_writable time ip ram load background_jobs)

# Customise the Powerlevel9k prompts
#POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(ssh dir vcs)
#POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(status root_indicator time)

# Set list of themes to pick from when loading at random
# Setting this variable when ZSH_THEME=random will cause zsh to load
# a theme from this variable instead of looking in ~/.oh-my-zsh/themes/
# If set to an empty array, this variable will have no effect.
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"

# Uncomment the following line to use hyphen-insensitive completion.
# Case-sensitive completion must be off. _ and - will be interchangeable.
# HYPHEN_INSENSITIVE="true"

# Uncomment the following line to disable bi-weekly auto-update checks.
# DISABLE_AUTO_UPDATE="true"

# Uncomment the following line to change how often to auto-update (in days).
# export UPDATE_ZSH_DAYS=13

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# Which plugins would you like to load?
# Standard plugins can be found in ~/.oh-my-zsh/plugins/*
# Custom plugins may be added to ~/.oh-my-zsh/custom/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(git kubectl)

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='mvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch x86_64"

# ssh
# export SSH_KEY_PATH="~/.ssh/rsa_id"

# Set personal aliases, overriding those provided by oh-my-zsh libs,
# plugins, and themes. Aliases can be placed here, though oh-my-zsh
# users are encouraged to define aliases within the ZSH_CUSTOM folder.
# For a full list of active aliases, run `alias`.
#
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"

#[ -s "/home/david/.scm_breeze/scm_breeze.sh" ] && source "/home/david/.scm_breeze/scm_breeze.sh"
#alias ls='ls -G'
#
#[ -s "/root/.scm_breeze/scm_breeze.sh" ] && source "/root/.scm_breeze/scm_breeze.sh"
#alias ls='ls -G'
