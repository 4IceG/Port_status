# Port_status

![GitHub release (latest by date)](https://img.shields.io/github/v/release/4IceG/Port_status?style=flat-square)
![GitHub stars](https://img.shields.io/github/stars/4IceG/Port_status?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/4IceG/Port_statuse?style=flat-square)
![GitHub All Releases](https://img.shields.io/github/downloads/4IceG/Port_status/total)

> [!NOTE]
> <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24">
> My small modification of "Port Status".   
> <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24">
> Moja mała modyfikacja "Statusu portów".

> [!IMPORTANT]
> <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24">   
> ***Change port label / description*** - click on the header   
> ***Change port order*** - drag and drop (grab the area around the icon)   
> <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24">   
> ***Zmiana etykiety / opisu portu*** - klikamy w nagłówek   
> ***Zmiana kolejności portów*** - przeciągnij i upuść (chwytamy za obszar wokół ikony)

> [!NOTE]
> <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24">
> ***Installation on a router:***

<details>
   <summary>Show me</summary>

1. Replace the contents of the 29_ports.js file using WinSCP (/www/luci-static/resources/view/status/include).
2. Change the permissions in luci-mod-status-index.json (/usr/share/rpcd/acl.d/luci-mod-status-index.json).
We search for the section with permissions for luci-mod-status-index-ports and replace it with this:   

``` bash
	"luci-mod-status-index-ports": {
	  "description": "Grant access to port status display",
		"read": {
			"file": {
				"/etc/user_defined_ports.json": [ "read" ]
			},
			"ubus": {
				"file": [ "read" ],
				"luci": [ "getBuiltinEthernetPorts" ]
			}
		},
		"write": {
			"file": {
				"/etc/user_defined_ports.json": [ "write" ]
			},
			"ubus": {
				"file": [ "write" ]
			}
		}
	},
```    
4. Cleare browser cache.
5. The first time, it created the /etc/user_defined_ports.json file, but it was empty. Repeate the configuration and We got what we want.
</details>

> [!NOTE]
> <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24">
> ***Instalacja na routerze:***

<details>
   <summary>Pokaż</summary>

1. Podmieniamy zawartość pliku 29_ports.js za pomocą WinSCP (/www/luci-static/resources/view/status/include)
2. Zmieniamy uprawnienia w luci-mod-status-index.json (/usr/share/rpcd/acl.d/luci-mod-status-index.json). Szukamy sekcji z uprawnieniami dla luci-mod-status-index-ports i podmieniamy na:   

``` bash
	"luci-mod-status-index-ports": {
	  "description": "Grant access to port status display",
		"read": {
			"file": {
				"/etc/user_defined_ports.json": [ "read" ]
			},
			"ubus": {
				"file": [ "read" ],
				"luci": [ "getBuiltinEthernetPorts" ]
			}
		},
		"write": {
			"file": {
				"/etc/user_defined_ports.json": [ "write" ]
			},
			"ubus": {
				"file": [ "write" ]
			}
		}
	},
```    
3. Czyścimy cache przeglądarki
4. Za pierwszym razem może utworzyć plik /etc/user_defined_ports.json ale pusty, ponawiamy konfigurację i już mamy to co być powinno.
</details>

> [!NOTE]
> <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24">
> ***Dodanie przy kompilacji:***

<details>
   <summary>Pokaż</summary>

1. Podmieniamy plik 29_ports.js w lokalizacji
   > /feeds/luci/modules/luci-mod-status/htdocs/luci-static/resources/view/status/include
2. Zmieniamy uprawnienia w luci-mod-status-index.json, plik znajduje się w
   > /feeds/luci/modules/luci-mod-status/root/usr/share/rpcd/acl.d/luci-mod-status-index.json.

	Szukamy sekcji z uprawnieniami dla luci-mod-status-index-ports i podmieniamy na:   
``` bash
	"luci-mod-status-index-ports": {
	  "description": "Grant access to port status display",
		"read": {
			"file": {
				"/etc/user_defined_ports.json": [ "read" ]
			},
			"ubus": {
				"file": [ "read" ],
				"luci": [ "getBuiltinEthernetPorts" ]
			}
		},
		"write": {
			"file": {
				"/etc/user_defined_ports.json": [ "write" ]
			},
			"ubus": {
				"file": [ "write" ]
			}
		}
	},
```    
3. Dodajemy tłumaczenie dla nowych okienek / elementów menu. Kopiujemy linijki tłumaczenia z pliku Port_status.pot do pliku w lokalizacji /feeds/luci/modules/luci-base/po/pl
4. Dopisujemy do pliku
   > /package/base-files/files/lib/upgrade/keep.d/base-files-essential

	na końcu nową linijkę /etc/user_defined_ports.json, aby zachować ustawienia poczynione przez użytkownika podczas generowania archiwum z kopią zapasową
</details>



### <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24"> Preview / <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24"> Podgląd

![](https://github.com/4IceG/Personal_data/blob/master/zrzuty/Port_status.gif?raw=true)
