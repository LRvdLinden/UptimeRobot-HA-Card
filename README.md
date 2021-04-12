# UptimeRobot Lovelace Card
Status updates in Home Assistant vanuit UptimeRobot
##### Created by Léon van der Linden
##### v1.0.0

![uptimerobot](https://scontent-ams4-1.xx.fbcdn.net/v/t1.6435-9/106796232_3593546114008659_9051489899601087280_n.png?_nc_cat=100&ccb=1-3&_nc_sid=e3f864&_nc_ohc=sN22nqAP2UIAX9HMuUx&_nc_ht=scontent-ams4-1.xx&oh=940a10cdf67cb438814c35f67c82dd23&oe=6096E7BB)

### Prerequisite
- Make a free [UptimeRobot](https://uptimerobot.com/) account and config what you want to monitor 
- Make sure you have installed the lovelace [uptime-card](https://github.com/dylandoamaral/uptime-card) and [fontawesome icons](https://github.com/thomasloven/hass-fontawesome). This can be done manually or directly via hacs

### Make Home Assistant intergration 
- Make the intergration with [UptimeRobot in Home Assistant](https://www.home-assistant.io/integrations/uptimerobot/)
 ```yaml
     # Example configuration.yaml entry
     binary_sensor:
       - platform: uptimerobot
         api_key: YOUR_API_KEY
```
- Restart Home Assistant

### Add code to the uptime-card
 ```yaml
   type: vertical-stack
   cards:
     - type: 'custom:uptime-card'
       entity: binary_sensor. # <-vul de sensor aan
       icon: 'fas:safari'
       name: cloud.....nl
       hours_to_show: 72
       status_adaptive_color: true
       average_text: '% uptime'
         alias:
           ok: Online
           ko: Offline
         color:
           icon: white
           ok: '#45C669'
           ko: '#C6B145'
           half: '#C66445'
           none: '#C9C9C9'
           title: white
         show:
           header: true
           title: true
           icon: true
           footer: true
           status: true
           timeline: true
           average: true
         tooltip:
            animation: true
          #tap_action:
            #action: url
            #url: 'https://'
```
- copy the above code into lovelace uptime-card
- add the correct `binary_sensor` to monitor
- fill in the correct `name:`
- add the `icon:` that you want to have
- when you want to use the `tap-action` function, delete `#` and fill in the `url: 'https/'` to the function
- when you want to monitor shorter or longer then 3 days, change the value `hours_to_show:`
- change the `alias:` `ok:` `ko:` name into `online`, `offline`, `up` or `down`
- copy the above string if you need more cards for more `binary_sensor`


### Result
![uptimerobot1](https://user-images.githubusercontent.com/77990847/114389788-bbe96680-9b95-11eb-85b0-4d584234f011.png)


