# DNSVideoCapture
Guide for capturing video of a console over a DNS server.

## Requirements
- A video gaming console with a built-in streaming service (such as PS4, PS5, Xbox, etc.)
- A PC running Windows or Linux

## Features
- [x] Use the console encoder
- [x] No need for an HDMI video capture device
- [x] No need for PS Remote Play
- [x] 1920 x 1080 60 fps
- [x] Has zero controller lag
- [x] Does not require an Ethernet connection.

## Step by Step
### Linux
1. Install **dnsmasq** on your favorite distro.
   - Ubuntu:
     > sudo apt-get install dnsmasq
   - Arch:
     > sudo pacman -Sy dnsmasq
   - Centos:
     > sudo yum install dnsmasq
2. Edit **/etc/resolv.conf**, should be looks like this
   > nameserver 8.8.8.8
   > 
   > nameserver [YOUR IP] (ex: 192.168.0.5)
   > 
3. Edit **/etc/dnsmasq.conf**, add some Twitch Ingest domain of your area. https://stream.twitch.tv/ingests/
   > server=/#/8.8.8.8
   > 
   > local=/localnet/
   > 
   > address=/scl01.contribute.live-video.net/[YOUR IP]
   > 
   > address=/bue01.contribute.live-video.net/[YOUR IP]
   > 
   > address=/sao05.contribute.live-video.net/[YOUR IP]
4. Open the following ports on your computer
   > 53 (DNS)
   > 
   > 1935 (RTMP)
5. Get the latest **red5-server** https://github.com/Red5/red5-server/releases
   - Rename red5-server/webapps/**live** -> red5-server/webapps/**app**
   - 
