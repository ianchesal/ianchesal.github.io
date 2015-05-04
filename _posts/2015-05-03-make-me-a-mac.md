---
layout: post
title: Make me a Mac!
---

I use Macs. I have for a while now. I have a short list of things I need to do when faced with a fresh OS X install. This isn't the comprehensive list of all the apps I touch in the course of a week or a month. Rather, it's the things I like to have on an OS X based machine to make it feel like mine, like home. It's the stuff I'd rather not get by without if I have to use an OS X-based machine. I use a lot of command line tools and my [dotfiles](https://github.com/ianchesal/dotfiles) and iTerm2 play big role in how I work with the command line. But there are some GUI apps I need as well.

* [LaunchBar](https://www.obdev.at/products/launchbar/index.html) ($29)  -- I don't like to leave my keyboard if I can help it and LaunchBar makes that possible. It's one of the few paid apps I really can't live without. Others will tell you Alfred, which can be had in a free form, is just as good but I have to disagree here. LaunchBar is just as tweak-able but out of the box does far more and it does with with a UI that I vastly prefer. The double-CTRL click to start an action on a file selected in the Finder is something I can't live without now. I use that to move and copy files incredibly frequently. And the TAB-to-send from within the bar is indespensible once you figure it out. I also have some [LaunchBar Actions](https://github.com/ianchesal/launchbar-actions) I've written that do nice things like gather all open Finder windows in to one window with tabs.

* [Google Chrome](https://www.google.com/chrome/) (free) -- I have a bad muscle memory from Cmd-1/2/3/4/5/etc. direct tab access and that's what mostly keeps me on Chrome. I did a week-with-Safari in December 2014 and just coudln't get around not having that shortcut sequence. I tried a SIMBL plugin for Safari that attempts to fix the problem but it doesn't work in Yosemite and, honestly, I don't care. Chrome is good enough.

* [lighthead Caffeine](http://itunes.apple.com/us/app/caffeine/id411246225) (free) -- It keeps your screen saver from kicking in. Useful if you have an enforced password screen saver policy and like to sit and stare at your screen when thinking. Also useful if you're working with things like Logic where you're not necessarily touching a mouse or keyboard for long periods of time, but you don't want your screen saver to start.

* [Agile Bits 1Password](https://agilebits.com/onepassword) ($49.99) -- Pick the password manager that suits you best, I like 1Password. Great UI. Great feature set. Sync'ing via Dropbox to all my machines and devices. I won't create a new account on a site without it. I really like it's site security feature for alerting you to compromised sites that might require your change your password and duplicate detection (not that you'll have any of those any more once you switch to auto-generated passwords). The multi-vault capabilities let you share a vault with a loved one too.

* [iTerm2](https://www.iterm2.com/) (free) -- Terminal is good. iTerm2 is better. I use its split window mode frequently. And for navigating multiple, identical servers, like a boss its `Broadcast Input` feature is awesome. It's as good a terminal as I've ever used.

* [Tapbots Tweetbot](https://itunes.apple.com/ca/app/tweetbot-for-twitter/id557168941?mt=12) ($19.99) -- Twitter is still my most-used social network and Tweetbot is still my favourite way to use it. It's even...gasp...been getting some updates on OS X lately. Though, honestly, it does what it does so well for me I'm a-okay with it not getting a lot of attention.

* [Homebrew](http://brew.sh/) (free) -- There are other package managers for OS X, but Homebrew's approach and simplicitly have fueled its metoric rise to fame over the long-time incumbents [Fink](http://www.finkproject.org/) and [MacPorts](https://www.macports.org/). It's easier to use. It organizes things in a nicely and easily-undone manner and it's got a good, active community that's always adding things and improving the packages. My essential list of Homebrew-managed packages I install is as follows:

```
git
git-flow
git-utils
jq
python
sqlite
tmux
vim
zsh
```

* [zsh](http://www.zsh.org/) (free) -- I switched from `bash` to `zsh` years ago. Combined with selective use of [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) plugins it's fast enough for me and rich enough in features and UI bling to make me happy. You can switch to the Homebrew-installed `zsh` by running: `brew install zsh; chsh -s /usr/local/bin/zsh; echo "/usr/local/bin/zsh" | sudo tee -a /etc/shells`. See my [dotfiles](https://github.com/ianchesal/dotfiles) for how I customize `zsh` and incorporate `oh-my-zsh` (which I try to use sparingly).

* [vim](http://www.vim.org/) (free) -- `vim` not `emacs`. Enough said. See my [dotfiles](https://github.com/ianchesal/dotfiles) for how I customize it. I made a big push to get good in vim late in 2014. I wanted to know a command line editor really well so no matter which server I roamed on to, I could do serious work without feeling hamstrung not having Sublime Text 2 around. It's been a good transition and there's no looking back now that I've got it tricked out the way I want I like it.

And that's it. The rest is gravy. I can do a full day's work programming or manager-ing with just the above and my [dotfiles](https://github.com/ianchesal/dotfiles).

What apps can't you live without when you sit down at an OS X machine?
