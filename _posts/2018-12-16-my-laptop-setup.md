---
layout: post
title: "My laptop setup"
description: Links and instructions for setting up a laptop just how I like it.
categories: "blog reference"
published: true
---

After setting myself up on four laptops in the space of two years, I figured it was time to write this all down. [Mike Gelbart's setup](https://github.com/mgelbart/misc/blob/master/laptop_setup.md) has been useful to me, so maybe mine will be useful to you.

## macOS preferences

1. Enable tap to click.
	- `System Preferences` → `Trackpad`
	- Check `Tap to click`
2. Set mouse speed to maximum.
	- `System Preferences` → `Trackpad`
	- Set `Tracking Speed` to `Fast`
3. Enable 3-finger drag.
	- `System Preferences` → `Trackpad` → `Accessibility`→ `Mouse & Trackpad` → `Trackpad Options` 
	- Check `Enable dragging` with `three finger drag`
4. Configure hot corners. 
	- `System Preferences` → `Trackpad` → `Hot Corners`
	- Top left: `Desktop`
	- Top right: `Mission Control`
	- Bottom left: `Put Display to Sleep`
	- Bottom right: `Launchpad`

## Installations

1. developer tools: `xcode-select --install`
2. [1Password](https://1password.com/)
3. [Chrome](https://www.google.ca/chrome/?brand=CHBD&gclid=Cj0KCQiAgMPgBRDDARIsAOh3uyLH9FyD5U6BuJ2Co_vlFaAEiDZYtHyFz2Wf-ESUYLTFpSxdpRLTXgQaAvyDEALw_wcB&gclsrc=aw.ds)
4. [Dropbox](https://www.dropbox.com/)
5. [Quicksilver](https://qsapp.com/)
6. [iTerm2](https://www.iterm2.com/)
7. [Homebrew](https://brew.sh/)
8. [f.lux](https://justgetflux.com/) `brew cask install flux`
9. [R](https://cran.rstudio.com/bin/macosx/)
10. [RStudio](https://www.rstudio.com/products/rstudio/download/)
11. [Anaconda](https://www.anaconda.com/download/#macos)
12. [MacDown](https://macdown.uranusjr.com/)
	- `Preferences` → `Rendering`
	- Check `TeX-like math syntax`
13. [Atom](https://atom.io/)
14. [Spotify](https://www.spotify.com/ca-en/download/other/)

## iTerm2 configurations

1. Set the default typing style  to Natural:
	- `Preferences` → `Profiles` → `Keys`
	- Set `Load preset` to `Natural Text Editing`
2. Set new windows/tabs to open from previous session's directory:
	- `Preferences` → `Profiles` → `General`
	- Under `Working Directory`, check `Reuse previous session's directory`

## Bash aliases

Put the following in `.bash_profile`:

```
alias macdown="open -a macdown"
alias rstudio="open -a rstudio"
alias slack="open -a slack"
alias atom="open -a atom"
alias preview="open -a preview"
```

## SSH

[Instructions](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

`ssh-add -K ~/.ssh/id_rsa` to store passphrase in Keychain.

Then add the following to `~/.ssh/config`:

```
Host *
  UseKeychain yes
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_rsa
```

## Git 

### Configure my user.

```
git config --global user.name "David Laing"
git config --global user.email davidkendalllaing@gmail.com
```

### Create a global gitignore file.

`touch ~/.gitignore_global`

Put this in it:

```
.DS_Store
.ipynb_checkpoints
.Trashes
.RHistory
.RData
__pycache__
```

### Set up git aliases.

```
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```

### Set up tab completion for git branches.

```
curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o ~/.git-completion.bash
```

Add this to `.bash_profile`:

```
if [ -f ~/.git-completion.bash ]; then
  . ~/.git-completion.bash
fi
```

Run `chmod -X ~/.git-completion.bash`, and restart iTerm2.

## RStudio configurations

### Change the default RStudio pane layout.

- `Preferences` → `Pane Layout`
- Top left: `Source`
- Top right: `Console`
- Bottom left: `History`
- Bottom right: everything else

### Add a margin line.

- `Preferences` → `Code` → `Display`
- Check `Show margin`

### Remove the default to save `.RData`.

- `Preferences` → `General`
- Uncheck `Restore .RData into workspace at startup`
- Change `Save workspace to .RData on exit` to `Never`

### Set up keyboard shortcuts.

- `Preferences` → `Code` → `Editing` → `Modify Keyboard Shortcuts`
- Open Previous Tab: `Alt+Cmd+Left`
- Open Next Tab: `Alt+Cmd+Right`
- Move focus to source: `Cmd+1`
- Move focus to console: `Cmd+2`
- Move focus to terminal: `Cmd+3`

### Create custom snippets.

- `Preferences` → `Code` → `Edit Snippets`
- Add these:

```
snippet pview
	{View(.); .}

snippet pprint
	{print(.); .}
```

## Jekyll

### [Install rbenv](https://jekyllrb.com/docs/installation/macos/) 

(So you don't have to alter the version of Ruby that comes with Mac.)

```
# Install rbenv and ruby-build
brew install rbenv

# Setup rbenv integration to your shell
rbenv init

# Check your install
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash

# Install a new version of Ruby
rbenv install 2.5.3
rbenv global 2.5.3
ruby -v
```

### Install Jekyll

[This post was useful](http://kbroman.org/simple_site/pages/local_test.html), as was [this issue comment](https://github.com/bundler/bundler/issues/1767#issuecomment-4787059).

```
gem install bundler
bundle install
```

To build a site:

```
bundle exec jekyll build
```

To test it locally:

```
bundle exec jekyll serve
```