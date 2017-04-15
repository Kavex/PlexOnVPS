# PlexOnVPS
Instruction on getting Plex to working on Ubuntu 16.04 x64 VPS 

Note: This is written for a fresh VPS with Ubuntu 16.04 x64

* Log into VPS via putty as root

* Install curl & update `sudo apt-get install curl & sudo apt-get update`

* Enable repository `echo deb https://downloads.plex.tv/repo/deb/ public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list & curl https://downloads.plex.tv/plex-keys/PlexSign.key | sudo apt-key add -`

* Install Plex `sudo apt-get update & sudo apt-get install plexmediaserver avahi-daemon`
