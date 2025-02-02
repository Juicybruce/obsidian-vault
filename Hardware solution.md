Need to pick and implement a media box that we can use to access local media.



#### Leading contender is a [Rapsberry Pi 5](https://raspberry.piaustralia.com.au/products/raspberry-pi-5?variant=44207825649888)

Advantages are:
- Multi-use - can serve beyond just being my media box in years to come + can act as a general server
- Custom Linux - I can set it up exactly how I want it
- Allows [[Enable game streaming]] via either steam link or Sunshine/Moonlight

Disadvantages:
- custom means cruft, it will need to be polished up to make sure it doesn't annoy Beth
- More work to get going
- Streaming sevices will either not work OR not work as well (limited by DRM to lower resolutions)

##### Operating system
Could use [LibreELEC](https://libreelec.tv/)?
- **No**, we can to use it for more than just kodi, so probably flash either ubuntu or PiOS

##### Networked or local storage?
- Networked is the final solution maybe, but our media consumption is maybe better suited to local (we cycle our media a fair bit)
	- Could just  `rync` a drive on my main PC on a cronjob to the pi
- could still use a solution like [Radarr](https://radarr.video/) , but trying to avoid having any hardware always on

##### Control?
HDMI-CEC might be able to pass through remote control commands from the TV receiver to the PI for the box to use

Or [flirc](https://flirc.tv/) make IR usb receivers / remotes

Or there are android / iOS apps you could use as a remote (dislike this option, too close to plex)


[I replaced my Apple TV—with a Raspberry Pi - Jeff Geerling](https://www.youtube.com/watch?v=3hFas54xFtg)
