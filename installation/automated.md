---
title: Automated Installation
layout: default
parent: Installation
nav_order: 2
---

# {{ page.title }}

If you want to host on a **Linux computer** or an **Android** phone, paste this command into Termux (an app on the Play Store) or a terminal:
```
(. <($(which curl>/dev/null&&echo curl -Ls||echo wget -qO-) https://gitlab.com/friendly-telegram/friendly-telegram/-/raw/master/install.sh))
```

If you want to host on **Windows** (7 and higher) paste this command into [Windows Powershell](http://www.powertheshell.com/topic/learnpowershell/firststeps/console):
```
iex (New-Object Net.WebClient).DownloadString("https://gitlab.com/friendly-telegram/friendly-telegram/-/raw/master/install.ps1")
```
Or for Heroku on **Windows**:
```
iex (New-Object Net.WebClient).DownloadString("https://gitlab.com/friendly-telegram/friendly-telegram/-/raw/master/install-heroku.ps1")
```

If you want to host on a **Mac** (and other *nix-like platforms that don't have `/dev/fd/*` or bash named pipe support)
```
$(which curl>/dev/null&&echo curl -LsO||echo wget -q) https://gitlab.com/friendly-telegram/friendly-telegram/-/raw/master/install.sh&&(. install.sh --no-web);rm install.sh
```
