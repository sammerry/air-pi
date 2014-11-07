# Air-PI

This is an [Ansible](#) script to provision a raspberry PI with the latest log monitoring software. It will Automatically start running [Beaver](#) a log daemon and push all data found in the /var/log folder to the Air Quality App servers. It will also setup the appropriate log rotation for beaver.log and airsensor.csv

### Installation (Mac)

Install [Brew](#)

```
brew install ansible
brew install brew-cask
brew cask install virtualbox
brew cask install vagrant
```

To test your build
```
vagrant up
```

### Deploying To Your PI

You will need to know the IP address of your RaspberryPI


### Log Rotation

- /var/log/beaver.log: every 4 weeks
- /var/log/airsensor.csv: ever 7 days

