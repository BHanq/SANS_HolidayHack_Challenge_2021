# Goal

Melt the entry access to the frost tower using WiFi CLI

# How

## Scanning

Look at scanning.png

Using iwlist wlan0 scan : to scan for the network

There is no key or security on it so we can connect without finding the key

It is location related so you must be close to the "WiFi" I believe the little blue circle on the wall is a WAP, pretty similar to Ubiquiti one (or it is maybe just the thermostat)

## Connect to the network

Use iwconfig wlan0 essid "FROST..." 

Once connected they gave us the webpage to the thermostat setup

## Gather setup page

curl http://nidus-setup:8080

Give us the API webpage

## API understanding

curl http://nidus-setup:8080/api

Explain how the thermostat works and tell us to not set temperature above 0 otherwise it could melt (what we want)

## Temperature modification

There is a command exemple (but with -40°) we just copy paste and modify to more than 0 (I put 10)

It is possible only because we don't need to register to use that command, otherwise we would have to register
