# Getting along with Fedora

## This is all about from for the first boot into fedora to the state I m satisfied this is what I want my development environment to be

## As I'm kind of into "distro-hopping" and have previous experince with the likes of Pop!\_OS, Linux Mint, Garuda, Ubuntu and Now Fedora being the newest editon to the list; So here I will try to add some documentation about the same

# &lt;&lt;&lt;|Here I will probably have to make an index|>>>

## Updating the system and it's packages

#### To check Update

```bash
dnf check-update
```

#### To start the Upgrade process after going through the list of updates available

```bash
sudo dnf upgrade
```

#### After the above is complete it's reccomended to reboot even though not neccessary; You can do the same by manual reboot or just run the below

```bash
sudo shutdown -r now
```

## Tweaks some setting as per your taste for example checking out the power mode and battery percentage

![Turn on Performance and Percentage in setting](./assets/turnOnPerformanceAndPercentage.png)

## Getting the minimise icon and dark mode with Gnome tools as there's no by default as you can see below

![No minimise by default lmao](./assets/noMinimiseIcon.png)

For that we have to install Gnome Tweaks so run the below

```bash
sudo dnf install gnome-tweaks
```

## Installing my personal favourites plugins with Gnome Shell Extentions

#### Clipboard Indicator _by Tudmotu_

#### Places Status Indicator _by fmuellner_

#### Caffeine _by eon_

#### Dash to Panel by _charlesg99_

#### Coverflow Alt-Tab by _p91paul_

#### Compiz alike windows effect _by hermes83_

#### Compiz alike magic lamp effect _by hermes83_

#### Compiz windows effect _by hermes83_

#### Transparent Window Moving _by Noobsai_

#### Resource Monitor _by Ory0n_

## Installing Vs Code

#### Importing the required packages

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
```

#### Installing

```bash
dnf check-update
sudo dnf install code
```

## Installing DISCORD

#### Getting relevant packages

```bash
sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

#### Checking for any updates just in case

```bash
sudo dnf update
```

#### Installing

```bash
sudo dnf install discord
```

> #### There might be issues where you can't screen share in zoom and discord this is due to the limited support of wayland so might just want to switch to Xorg

## Installing Java

#### Serching about all the available versions

```bash
dnf search openjdk
```

#### I lean to installing the legacy java 1.8.0 and the latest for mental peace that I have best of both

```bash
sudo dnf install java-1.8.0-openjdk.x86_64
sudo dnf install java-latest-openjdk.x86_64
```

#### Run this to finish it off

```bash
sudo dnf install java-latest-openjdk-devel.x86_64
```

#### After installing to know the active java version

```bash
java -version
```

#### To switch between the existing java versions

```bash
sudo alternatives --config java
```

## What are those Fedora outdated versions in grub boot menu

#### By default, Fedora keeps the last 3 kernels to be on the safe side. So in case the newest kernel doesn’t work as well as it should with your hardware, you can reboot into an older one. These are what you see in your grub boot menu.


credit : [Ankur Sinha] (https://ask.fedoraproject.org/u/ankursinha)

Limit battery charger %
The limit in charging % laptop to 60/80% for helps for better battery health
sudo vi  /etc/crontab

@reboot sudo echo 80 | sudo tee /sys/class/power_supply/BAT0/charge_control_end_threshold

sudo echo 80 | sudo tee /sys/class/power_supply/BAT0/charge_control_end_threshold

@reboot sudo echo 80 | sudo tee /sys/class/power_supply/BAT0/charge_control_end_threshold

Open a new or existing file with vim filename .
Type i to switch into insert mode so that you can start editing the file.
Enter or modify the text with your file.
Once you're done, press the escape key Esc to get out of insert mode and back to command mode.
Type :wq to save and exit your file


update vim

install crontab

```
dnf install cronie cronie-anacron
```

use command to edit crontab

save

enjoy

MISC
https://github.com/VundleVim/Vundle.vim

https://www.freecodecamp.org/news/vimrc-configuration-guide-customize-your-vim-editor/


https://stackoverflow.com/questions/5952467/how-to-specify-a-editor-to-open-crontab-file-export-editor-vi-does-not-work
