---
title: QNAP Container-Station Installation
layout: default
parent: Installation
nav_order: 5
---

# {{ page.title }}


In order to host on QNAP, you can use the Container-Station.


Add Gitlab Registry to the Container Station:
 - First open Container Station, open `Images` on the left
 - Press top right on `Pull`. There you get a new window for adding Registrys
 - Add a new Registry for Gitlab: `https://registry.gitlab.com`
 - Press on Test and apply

Pull FTG to Container Station:
 - Go to `Images` and press on `Pull`
 - Image-Name: `friendly-telegram/friendly-telegram`
 - Image-Tag: `latest`
 - Press on `Pull`

Create Container:
 - Press on `+` on the right of the FTG Container
 - Press on `Advanced Settings`
 - Press on Network and set `Host` to the port 8080
 - On `Share` you can add some Folders. Example: Hostpath `/share/Multimedia` | Mount Point: `/app/multimedia`

After its done, log into the webinterface and setup the Bot as usual... After the bot is up you need to tweak the container by following commands, since the container lacks some packages and folders to function:

Telegram .terminal commands:
 - `.terminal mkdir /tmp && chmod 1777 /tmp`
   Create missing /tmp dir and permissions.
 - `.terminal apt-get update && apt-get dist-upgrade -y && apt-get install -y --no-install-recommends apt-utils && apt-get install -y dialog && apt-get install -y whiptail && apt-get install -y sudo && apt-get install -y wget && apt-get install -y curl`
   Updating system and install missing pkgs, this will take a while!

When you want to restart or stop the userbot, simply do it via Container Station
