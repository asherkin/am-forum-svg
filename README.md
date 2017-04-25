### Helpers

**TODO**
```
	"/images/btn_donate_SM.gif"
	"/images/buttons/collapse_thead.gif"
	"/images/misc/menu_open.gif"
	"/images/statusicon/subforum_new.gif"
	"/images/statusicon/subforum_old.gif"
```

**Get All Images**
```
Array.from(document.getElementsByTagName('img'))
	.map(i => i.src)
	.filter(s => s.substr(0, 30) === 'https://forums.alliedmods.net/')
	.map(s => s.substr(29))
	.filter((s, i, a) => a.indexOf(s) === i)
	.sort();
```

**Image Mapping**
```
var imageMap = {
	"/images/buttons/collapse_tcat.gif": "collapse_tcat.svg",
	"/images/buttons/collapse_tcat_collapsed.gif": "collapse_tcat_collapsed.svg",
	"/images/buttons/lastpost.gif": "lastpost.svg",
	"/images/misc/am-banner.png": "am-banner.svg",
	"/images/misc/stats.gif": "stats.svg",
	"/images/misc/whos_online.gif": "whos_online.svg",
	"/images/statusicon/forum_link.gif": "forum_link.svg",
	"/images/statusicon/forum_new.gif": "forum_new.svg",
	"/images/statusicon/forum_old.gif": "forum_old.svg",
	"/images/misc/birthday.gif": "birthday.svg",
	"/images/statusicon/user_offline.gif": "user_offline.svg",
	"/images/statusicon/user_online.gif": "user_online.svg",
	"/images/buttons/infraction.gif": "infraction.svg",
	"/images/buttons/ip.gif": "ip.svg",
	"/images/buttons/nuke.gif": "nuke.svg",
	"/images/buttons/report.gif": "report.svg",
	"/images/buttons/unnuke.gif": "unnuke.svg",
	"/images/buttons/collapse_thead.gif": "collapse_thead.svg",
	"/images/buttons/collapse_thead_collapsed.gif": "collapse_thead_collapsed.svg",
};
Array.from(document.getElementsByTagName('img'))
	.filter(i => i.src.substr(0, 30) === "https://forums.alliedmods.net/")
	.forEach(i => { imageMap[i.src.substr(29)] && (i.src = "https://fennec.limetech.io/am-forum-svg/" + imageMap[i.src.substr(29)] + "?d=" + Date.now()); });
```
