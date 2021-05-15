<h1 align="center">UptimeRobot Lovelace Card</h1>

<p align="center">
    <a href="https://github.com/LRvdLinden/UptimeRobot-HA-Card/commits">
    <img src="https://img.shields.io/github/last-commit/LRvdLinden/UptimeRobot-HA-Card.svg?style=plasticr" />
  </a>
  <a href="https://github.com/LRvdLinden/UptimeRobot-HA-Card/">
    <img src="https://img.shields.io/github/v/release/LRvdLinden/UptimeRobot-HA-Card" />
  </a>
    <a href="https://github.com/LRvdLinden/">
    <img src="https://img.shields.io/github/followers/LRvdLinden?style=social" />
  </a>
    </a>
    <a href="https://discord.gg/7yt64uX">
    <img src="https://img.shields.io/discord/688401603811999885" />
  </a>
  
<p align="center">A minimalist card inspired by the <a href="https://github.com/dylandoamaral/uptime-card">Uptime-card</a> to display UptimeRobot binary sensors in a nice way.</p>


<p align="center">Created by <a href="https://github.com/LRvdLinden">Léon van der Linden</a> based on <a href="https://github.com/dylandoamaral/uptime-card">uptime-card</a> created by <a href="https://github.com/dylandoamaral/uptime-card">Dylandoamaral</a>
</p> 



![uptimerobot](https://scontent-ams4-1.xx.fbcdn.net/v/t1.6435-9/106796232_3593546114008659_9051489899601087280_n.png?_nc_cat=100&ccb=1-3&_nc_sid=e3f864&_nc_ohc=sN22nqAP2UIAX9HMuUx&_nc_ht=scontent-ams4-1.xx&oh=940a10cdf67cb438814c35f67c82dd23&oe=6096E7BB)

## Prerequisite
---
- Make a free [UptimeRobot](https://uptimerobot.com/) account and config what you want to monitor 
- Make sure you have installed the lovelace [uptime-card](https://github.com/dylandoamaral/uptime-card) and [fontawesome icons](https://github.com/thomasloven/hass-fontawesome). This can be done manually or directly via hacs

## Make Home Assistant integration 
---
- Make the integration with [UptimeRobot in Home Assistant](https://www.home-assistant.io/integrations/uptimerobot/)
 ```yaml
     # Example configuration.yaml entry
     binary_sensor:
       - platform: uptimerobot
         api_key: YOUR_API_KEY
```
- Restart Home Assistant

## Add code to the uptime-card
---
 ```yaml
type: 'custom:uptime-card'
entity: binary_sensor.homeassistant
icon: 'fas:safari'
name: Home Assistant
hours_to_show: 72
status_adaptive_color: true
average_text: '% uptime'
alias:
  ok: Online
  ko: Offline
blink:
  effect: fade
  target: card
  speed: 1
color:
  icon: gray
  ok: '#45C669'
  ko: '#C6B145'
  half: '#C66445'
  none: '#C9C9C9'
  title: gray
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
tap_action:
action: url
url_path: 'https://YOUR.NABU.CASA.URL'
```
- copy the above code into lovelace uptime-card
- add the correct `binary_sensor` to monitor
- fill in the correct `name:`
- add the `icon:` that you want to have
- when you want to use the `tap-action` function, fill in the right `url: 'https/'` to the function
- when you want to monitor shorter or longer then 3 days, change the value `hours_to_show:`
- change the `alias:` `ok:` `ko:` name into `online`, `offline`, `up` or `down`
- copy the above string if you need more cards for more `binary_sensor`

## Configuration ⚙️
---
Uptime card is highly customizable. See Github [Uptime Card](https://github.com/dylandoamaral/uptime-card) for all the options


## Result
---
![uptimerobot1](https://user-images.githubusercontent.com/77990847/114389788-bbe96680-9b95-11eb-85b0-4d584234f011.png)

---
Enjoy my card? Help me out for a couple of :beers: or a :coffee:!

[![coffee](https://www.buymeacoffee.com/assets/img/custom_images/black_img.png)](https://www.buymeacoffee.com/LRvdLinden)
