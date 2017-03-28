# Install the dependencies

`sudo apt-get install open-vm-tools htop nload iotop sudo curl -y`

# Add the current user to the Sudo Group

`sudo adduser kay sudo`

# Install Node.js

```
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
```

# Install http-server

`sudo npm -g install http-server`

# Install Git / JSMpeg

```
sudo apt-get install git
git clone https://github.com/phoboslab/jsmpeg.git
```

`cd jsmpeg/`

# Install WS in the jsmpeg folder

`npm install ws`

# Make sure the scripts / services are started at startup

`sudo nano /etc/cron.d/startup`

## Put the following in: 

```
@reboot kay nohup node /home/kay/jsmpeg/websocket-relay.js password 8081 8082
@reboot kay nohup http-server /home/kay/jsmpeg -p 8080
@reboot kay nohup avconv -r 30 -i rtsp://192.168.100.151:7447/58afee94c2dc2fb7893182c6_0 -f mpegts -codec:v mpeg1video -s 1024x576 -b:v 2048k -bf 0 -an http://192.168.100.144:8081/password 
```

View the result on: `https://192.168.100.144:8080/view-stream.html`
