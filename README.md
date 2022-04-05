# guillaumecatel/dotfiles

> 🔧 Dotfiles, including Oh My Zsh, P10K, Brew and .macos.

## Installation

### Git (XCode)

Install it on the command line first, it will ask for permission.

```
xcode-select --install
```

### Dot files

```
git clone https://github.com/guillaumecatel/dotfiles
cd dotfiles
```

Sync the files.

```
./bootstrap.sh
```

Apply macOS settings.

```
./.macos
```

Install Homebrew and OhMyZSH.

```
./brew_once.sh
```

### Install tools and apps

Install tools and applications with Homebrew bundle.

```
brew bundle
```

This makes use of the [Brewfile](Brewfile) definitions.

[mas](https://github.com/mas-cli/mas) is used to install apps from the app store, and is itself installed with Homebrew first in the [Brewfile](Brewfile).

## Upgrades

On major version upgrades, binaries might be incompatible or need a local rebuild.
You can enforce a reinstall by running the two commands below, the second command
only reinstalls all application casks.

```
brew reinstall $(brew list)

brew reinstall $(brew list --cask)
```

When Xcode and compilers break, re-install the command line tools.

```
sudo rm -rf /Library/Developer/CommandLineTools
sudo xcode-select --install
```

## License
MIT
