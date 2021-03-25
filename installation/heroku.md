---
title: Heroku Installation
layout: default
parent: Installation
nav_order: 3
---

# {{ page.title }}

## Deploy button

You can directly click [![Deploy](https://www.herokucdn.com/deploy/button.svg)](
https://www.heroku.com/deploy/?template=https://github.com/friendly-telegram/gitlab-mirror) to deploy to Heroku. Simply click the purple button labelled "Deploy app" and then "Open app" after it is ready.

## Script

Follow the instruction in [automated setup](../automated/) but change the command used to
```
(. <($(which curl>/dev/null&&echo curl -Ls||echo wget -qO-) https://gitlab.com/friendly-telegram/friendly-telegram/-/raw/master/install.sh) --heroku)
```
