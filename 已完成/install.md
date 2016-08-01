## System Preferences

```bash
# Enable character repeat on keydown
defaults write -g ApplePressAndHoldEnabled -bool false

# Set a shorter Delay until key repeat		
defaults write NSGlobalDomain InitialKeyRepeat -int 12

# Set a blazingly fast keyboard repeat rate
defaults write NSGlobalDomain KeyRepeat -int 2

# Disable window animations ("new window" scale effect)
defaults write NSGlobalDomain NSAutomaticWindowAnimationsEnabled -bool false

# Use plain text mode for new TextEdit documents
defaults write com.apple.TextEdit RichText -int 0

# Set default Finder location to home folder (~/)
defaults write com.apple.finder NewWindowTarget -string "PfLo" && \
defaults write com.apple.finder NewWindowTargetPath -string "file://${HOME}"

# Expand save panel by default
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true

# Check for software updates daily, not just once per week
defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1

# Use current directory as default search scope in Finder
defaults write com.apple.finder FXDefaultSearchScope -string "SCcf"

# Show Path bar in Finder
defaults write com.apple.finder ShowPathbar -bool true

# Show Status bar in Finder
defaults write com.apple.finder ShowStatusBar -bool true

# Show icons for hard drives, servers, and removable media on the desktop
defaults write com.apple.finder ShowExternalHardDrivesOnDesktop -bool true && \
defaults write com.apple.finder ShowHardDrivesOnDesktop -bool true && \
defaults write com.apple.finder ShowMountedServersOnDesktop -bool true && \
defaults write com.apple.finder ShowRemovableMediaOnDesktop -bool true

# Avoid creating .DS_Store files on network volumes
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true

# Enable the Develop menu and the Web Inspector in Safari
defaults write com.apple.Safari IncludeInternalDebugMenu -bool true && \
defaults write com.apple.Safari IncludeDevelopMenu -bool true && \
defaults write com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true && \
defaults write com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true && \
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

# Show the ~/Library folder
chflags nohidden ~/Library

# Show absolute path in finder's title bar. 
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES

# Show build duration for Xcode
defaults write com.apple.dt.Xcode ShowBuildOperationDuration YES

```

## Shell

#### Install XCode first

```
# install xcode command tool
xcode-select --install
# check
xcode-select -p

```

#### Homebrew

```

# install brew
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"

# check brew
brew doctor
brew update

# turn off analytics
brew analytics off


```

```bash
# Install homebrew packages
brew install \
wget \
ssh-copy-id \
zsh \
keybase \
mackup \
mobile-shell \
mtr \
nmap \
pyenv \
tmux \
youtube-dl \
git \
tree \
caskroom/cask/brew-cask \
mackup 

```

### oh-my-zsh
```bash
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```


#### Homebrew Cask Apps & Fonts


Please Visit [https://gist.github.com/HenryYang/af43f7421ac7de019b93](https://gist.github.com/HenryYang/af43f7421ac7de019b93) to see more detail


### Set hostname

```bash
sudo scutil --set HostName empp
```


```bash
mackup restore
```

### iTerm2

```bash
# Install Solarized Dark theme for iTerm2
wget http://ethanschoonover.com/solarized/files/solarized.zip -O ~/Downloads/solarized.zip
unzip ~/Downloads/solarized.zip -d ~/Downloads/
open ~/Downloads/solarized/iterm2-colors-solarized/Solarized\ Dark.itermcolors

# Install Menlo Regular for Powerline font
wget https://raw.githubusercontent.com/supermarin/powerline-fonts/master/Menlo/Menlo%20Regular%20for%20Powerline.otf -O ~/Downloads/Menlo\ Regular\ for\ Powerline.otf
open ~/Downloads/Menlo\ Regular\ for\ Powerline.otf



```


