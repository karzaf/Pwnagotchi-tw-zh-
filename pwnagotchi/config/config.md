# Config.toml
```
main.name "changeme"                                                  #Display name by paper.
main.lang "changeme"                                                  #Lang : en, bg, ch, de, el, es, fr, ga, it, jp, mk, nl, no, pl, pt, pt-BR, ro, ru, se, sk, ua
main.whitelist = [
  "allow_access",
  "YourHomeNetworkHere",
]

main.plugins.grid.enabled = true                                       #Enable PwnGrid
main.plugins.grid.report = true                                        #Report pwned networks
main.plugins.auto-update.enabled = false                               #Don't update ,if update not yet fix problem, that could be crash!!!

main.plugins.grid.exclude = [
  "allow_access",
  "YourHomeNetworkHere",
]                                                                      #Don't report exclude list network

ui.display.enabled = true                                              #Enable display by paper
ui.display.type =  "changeme"                                          #Also waveshare version info label form paper model
ui.display.color = "changeme"                                          #black or white
ui.fps = 0.0                                                           #Fps 0~3 maximum range of paper

ui.web.address = "0.0.0.0"                                             #Web ui access
ui.web.username = "changeme"                                           #Change Web ui user
ui.web.password = "changeme"                                           #Chahge Web ui password
ui.web.port = 8080                                                     #Change customize port to access web ui 

main.plugins.bt-tether.enabled = true                                  #Enable bluetooth connect
main.plugins.bt-tether.devices.android-phone.enabled = true            #Enable bluetooth connect to android devices
main.plugins.bt-tether.devices.android-phone.mac = "changeme"          #Mac address = setting->info moble phone-> state info -> bluetooth access
main.plugins.bt-tether.devices.android-phone.ip = "changeme"           #Defaults is 192.168.44.44, can change any ip range of 192.168.

main.plugins.memtemp.enabled = true                                    #Display memory usage, cpu load and cpu temperature on screen

main.log.path = "/var/log/pwnagotchi.log"                              #Change which path folder your save
main.log.rotation.size = "10M"                                         #File size

ai.enabled = true                                                      #Enable AI
ai.path = "/root/brain.nn"                                             #Which file path of ai 
ai.epochs_per_episode = 50                                             #How many epochs to train on

personality.deauth = false                                             #perform a deauthentication attack to client stations in order to get full or half handshakes

#emoticon https://smiley.cool/emoticons.php , https://facemood.grtimed.com/ 
ui.faces.look_r = "( ⚆_⚆)"
ui.faces.look_l = "(☉_☉ )"
ui.faces.look_r_happy = "( ◕‿◕)"
ui.faces.look_l_happy = "(◕‿◕ )"
ui.faces.sleep = "(⇀‿‿↼)"
ui.faces.sleep2 = "(≖‿‿≖)"
ui.faces.awake = "(◕‿‿◕)"
ui.faces.bored = "(-__-)"
ui.faces.intense = "(°▃▃°)"
ui.faces.cool = "(⌐■_■)"
ui.faces.happy = "(•‿‿•)"
ui.faces.excited = "(ᵔ◡◡ᵔ)"
ui.faces.grateful = "(^‿‿^)"
ui.faces.motivated = "(☼‿‿☼)"
ui.faces.demotivated = "(≖__≖)"
ui.faces.smart = "(✜‿‿✜)"
ui.faces.lonely = "(ب__ب)"
ui.faces.sad = "(╥☁╥ )"
ui.faces.angry = "(-_-')"
ui.faces.friend = "(♥‿‿♥)"
ui.faces.broken = "(☓‿‿☓)"
ui.faces.debug = "(#__#)"
ui.faces.upload = "(1__0)"
ui.faces.upload1 = "(1__1)"
ui.faces.upload2 = "(0__1)"
```
## Bettercap rest api
```
bettercap.scheme = "http"                  #http or https
bettercap.hostname = "localhost"           #localhost or ddns.com
bettercap.port = 8081                      #Edit port for web ui
bettercap.username = "changeme"            #battercap web ui username
bettercap.password = "changeme"            #battercap web ui password
bettercap.handshakes = "/root/handshakes"  #Which path to watch pcap file
```

## GPS Pulgin Configurations
if have gps plugin, you can follewing that one:
```
main.plugins.gps.enabled = true
main.plugins.gps.speed = 9600
main.plugins.gps.device = "/dev/ttyUSB0"
```

## File path
* ai = ```/root/brain.nn```
* ai config =```/root/brain.json```
* api =```/root/.api-report.json```
* pcap =```/root/handshakes/```
* config = ```/etc/pwnagotchi/```
* log = ```/var/log/pwnagotchi.log```
