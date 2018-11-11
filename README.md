# Startguide - lgtv-alexa-skill
## Node.js bridge for LG webOS TVs + Amazon Alexa

### Modification Notes
- The original bridge software (by https://github.com/lucone83) has been modified to install as a Docker Container specifically for installation into an Unraid Server platform. The Docker template repository can be accessed from https://github.com/bigbadblo/docker-templates.

### Unraid Requirements
- Node.js will need to be installed and accessible in Unraid for this bridge to function. NerdPack GUI (http://lime-technology.com/forum/index.php?topic=37541.0) allows for easy installation of node.js via the NerdPack Settings App in Unraid. 

### Unraid Configuration
- Upon adding the Docker container image, update "tvMAC" and "tvIP" fields to accurately reflect your television's unique settings. Recommendation is to set your tv's IP address to either manual IP (via the Network settings on your LG TV) or static IP (via your router) in order to prevent issues down the road.

### To Do on First Run
- Be sure your Alexa-ready device is up and running
- On your TV, make sure that _TV Mobile On_ (General settings) is set to ON
- On your TV, make sure that _LG Connect Apps_ (Network settings) is set to ON
- Add the devices using the Alexa app (`Settings -> Smart Home -> Add Device `)
- Wait about a minute, then say "Alexa turn TV on/off" or "Alexa start/stop [app name]"
- **Important The first time, turning on/off the TV will ask for permission; just confirm the pairing via prompt on your tv and your bridge is ready!**

### Available Functions (used from the Docker Container Console)
**Alexa bridge**<br/>
`node index.js alexa` - Makes the vocal commands for TV and apps available

**Toast**<br/>
`node index.js toast "[your message]"` - Display a toast message on your TV

**Apps List**<br/> 
`node index.js appslist` - Display all the apps installed on your Smart TV and provides some useful info (appID etc.)

**Service list**<br/>
`node index.js serviceslist` - Display a list of the available services and theirs API

**Status**<br/>
`node index.js status` - Display the TV status (ON or OFF), and if ON, shows the application in use

**Application status**<br/>
`node index.js appstatus [app ID]` - Display the status of the application specified by an ID

**Mute on/off**<br/>
`node index.js mute [true|false]` - Mute/Unmute your TV

**Turn TV on/off**<br/>
`node index.js [tvon|tvoff]` - Turn the TV on or off

### Available Voice Commands
- **Turn tv on/off**: "Alexa, turn TV [on|off]"
- **Start/stop application**: "Alexa, turn \[on|off\] \[your app\]" or "Alexa,\[start|stop\] \[your app\]"
- **Mute/unmute tv**: "Alexa, turn _muting mode_ \[on|off\]"

### Available Applications
- Netflix ("Netflix")
- Amazon Prime ("Prime")
- MLB TV ("MLB")
- Plex ("Plex")
- HDMI Input 1 ("HDMI One")
- HDMI Input 2 ("HDMI Two")

### Add Additional Applications (Unraid inclusion TBD)
It's possible to add your own application if you know the appID (and if you don't just run the `appslist` command to get a list). Add your application on `apps.json`, restart the Alexa bridge and run the device discovery on Alexa app on your mobile or at the [Alexa website](https://alexa.amazon.com).

### Thanks to original work conducted by
- [lucone83, forked lgvt-alexa-skill](https://github.com/lucone83/lgtv-alexa-skill)
- [hobbyquacker, lgtv2 library](https://github.com/hobbyquaker/lgtv2)
- [neil-morrison-44, forked project](https://github.com/neil-morrison44/lg-alexa-node)

### Special thanks to the one and only
- [sbeckeriv](https://github.com/sbeckeriv)
