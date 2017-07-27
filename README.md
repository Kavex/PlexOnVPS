# PlexOnVPS
Instruction on getting Plex to working on Ubuntu 16.04 x64 VPS 

Note: This is written for a fresh VPS with Ubuntu 16.04 x64

* Log into VPS via putty as root/sudoer

* Install updates `sudo apt-get update && sudo apt-get upgrade`

* wget plex `wget https://downloads.plex.tv/plex-media-server/1.7.5.4035-313f93718/plexmediaserver_1.7.5.4035-313f93718_amd64.deb`

* Install Plex `sudo dpkg -i plexmediaserver*.deb`

* Add plex as a service `sudo systemctl enable plexmediaserver.service && sudo systemctl start plexmediaserver.service`

* Open port 32400 `sudo iptables -A INPUT -p tcp -d 0/0 -s 0/0 --dport 32400 -j ACCEPT`

* Make media dir `sudo mkdir /home/plex/ && sudo chown -v -R plex:plex /home/plex/`

* Open new putty session and add the server ip in Host Name and go under “Connection > SSH > Tunnels > Add new forwarded port” set the following
`Source port: 32400` and `Destination: localhost:32400`

* Go to a browser `http://localhost:32400/web/index.html`

Other guides

https://community.time4vps.eu/discussion/123/plex-how-to-install-plex-media-center-on-ubuntu
