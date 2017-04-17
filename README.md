# PlexOnVPS
Instruction on getting Plex to working on Ubuntu 16.04 x64 VPS 

Note: This is written for a fresh VPS with Ubuntu 16.04 x64

* Log into VPS via putty as root

* Install curl & update `apt-get update && sudo apt-get install curl avahi-daemon`

* Enable repository `echo deb https://downloads.plex.tv/repo/deb/ public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list && curl https://downloads.plex.tv/plex-keys/PlexSign.key | sudo apt-key add -`

* Install Plex `sudo apt-get update && sudo apt-get install plexmediaserver`

* Open port 32400 `sudo iptables -A INPUT -p tcp -d 0/0 -s 0/0 --dport 32400 -j ACCEPT`

* Open new putty session and add the server ip in Host Name and go under “Connection > SSH > Tunnels > Add new forwarded port” set the following
`Source port: 32400` and `Destination: localhost:32400`

* Go to a browser `http://localhost:32400/web/index.html`

Other guides

https://community.time4vps.eu/discussion/123/plex-how-to-install-plex-media-center-on-ubuntu




