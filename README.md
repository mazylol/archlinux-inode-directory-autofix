# Archlinux inode/directory Autofix
Some applications such as vscode and zed automatically make themselves the default app to open files. This is incredibly annoying. It is an easy fix but you have to do it every time pacman updates mimeinfo.cache file. This python script and accompanying pacman hook automatically do it for you.

## Setup
1. Copy `99-fixmime.hook` to `/etc/pacman.d/hooks/`
2. Edit fixmime to open your desired app of choice, with backups
    - Unless you are ok with nautilus, which is what I use
3. Put `fixmime` somewhere in your path
4. Optionally, run the script (with sudo) to fix it for the first time, after that it will automatically do it on pacman installs/updates

## Note
If you are confused about the hook starting a systemd service. It is so that the script runs after your mimeinfo is updated. I could not for the life of me get the hook to run after the mimeinfo hook so I resorted to having a 5 second delay. If anyone knows how to make it run after without the delay, please make a PR!
