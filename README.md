# Port_status

![GitHub release (latest by date)](https://img.shields.io/github/v/release/4IceG/Port_status?style=flat-square)
![GitHub stars](https://img.shields.io/github/stars/4IceG/Port_status?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/4IceG/Port_statuse?style=flat-square)
![GitHub All Releases](https://img.shields.io/github/downloads/4IceG/Port_status/total)

> [!NOTE]
> <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24">
> My small modification of "Port Status".
>
> <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24">
> Moja mała modyfikacja "Statusu portów".

> [!IMPORTANT]
> ***Change port label / description*** - click on the header   
> ***Change port order*** - drag and drop (grab the area around the icon)
> 
> 
> ***Zmiana etykiety / opisu portu*** - klikamy w nagłówek   
> ***Zmiana kolejności portów*** - przeciągnij i upuść (chwytamy za obszar wokół ikony)

> [!IMPORTANT]
> ***Path to file / Ścieżka do pliku:***   
> ***Compilation / Kompilacja:***
> /feeds/luci/modules/luci-mod-status/htdocs/luci-static/resources/view/status/include   
> ***Router:***
> /www/luci-static/resources/view/status/include
> 
> ***Translation of new windows / menu elements:***   
> ***Copy translation from Port_status.pot to file:***
> /feeds/luci/modules/luci-base/po/xx   
> ***Tłumaczenie nowych okien / elementów menu:***   
> ***Skopiuj zawartość Port_status.pot do pliku:***
> /feeds/luci/modules/luci-base/po/xx

> [!IMPORTANT]
> ***Modification of permissions / Modyfikacja uprawnień:***   
> ***Path to file / Ścieżka do pliku:***   
> ***Compilation / Kompilacja:***
> /feeds/luci/modules/luci-mod-status/root/usr/share/rpcd/acl.d/luci-mod-status-index.json   
> ***Router:***
> /usr/share/rpcd/acl.d/luci-mod-status-index.json

<details>
   <summary>Pokaż | Show me</summary>

``` bash
 	"luci-mod-status-index-ports": {
	  "description": "Grant access to port status display",
	  "read": {
	    "ubus": {
	      "luci": [ "getBuiltinEthernetPorts" ]
	    },
	    "file": {
	      "/etc/user_defined_ports.json": ["read"]
	    }
	  },
	  "write": {
	    "file": {
	      "/etc/user_defined_ports.json": ["write"]
	    }
	  }
	},
```
</details>

> [!IMPORTANT]
> ***Currently works on Openwrt after compilation / Aktualnie działa na Openwrt po kompilacji***

### <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24"> Preview / <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24"> Podgląd

![](https://github.com/4IceG/Personal_data/blob/master/zrzuty/Port_status.gif?raw=true)
