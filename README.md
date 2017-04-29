### Helpers

**TODO**
```
	"/clear.gif": "",
 	"/images/btn_donate_SM.gif": "",
 	"/images/buttons/newthread.gif": "",
```

**Style Changes**
```
Add `margin: 0 10px;` to left forum icons on forum index.
.tcat .inlineimg { vertical-align: text-bottom; }
Add `vertical-align: baseline;` to lastpost image on right of forum index.
Adjust vertical-align of post header buttons (post_old, edit, quote, reply etc).
multipage.svg = vertical-align: text-bottom
```

**Get All Images**
```
Array.from(document.getElementsByTagName('img'))
	.map(i => i.src)
	.filter(s => s.substr(0, 30) === 'https://forums.alliedmods.net/')
	.map(s => s.substr(29))
	.filter((s, i, a) => a.indexOf(s) === i)
	.sort()
	.forEach(s => console.log("\t\"" + s + "\": \".svg\","));
```

**Image Mapping**
```
var imageMap = {
	"/images/buttons/collapse_tcat.gif": "collapse_tcat.svg",
	"/images/buttons/collapse_tcat_collapsed.gif": "collapse_tcat_collapsed.svg",
	"/images/buttons/collapse_thead.gif": "collapse_thead.svg",
	"/images/buttons/collapse_thead_collapsed.gif": "collapse_thead_collapsed.svg",
	"/images/buttons/firstnew.gif": "firstnew.svg",
	"/images/buttons/infraction.gif": "infraction.svg",
	"/images/buttons/ip.gif": "ip.svg",
	"/images/buttons/lastpost.gif": "lastpost.svg",
	"/images/buttons/nuke.gif": "nuke.svg",
	"/images/buttons/report.gif": "report.svg",
 	"/images/buttons/sortasc.gif": "sortasc.svg",
 	"/images/buttons/sortdesc.gif": "sortdesc.svg",
	"/images/buttons/unnuke.gif": "unnuke.svg",
	"/images/misc/am-banner.png": "am-banner.svg",
	"/images/misc/birthday.gif": "birthday.svg",
	"/images/misc/menu_open.gif": "menu_open.svg",
 	"/images/misc/multipage.gif": "multipage.svg",
 	"/images/misc/paperclip.gif": "paperclip.svg",
	"/images/misc/stats.gif": "stats.svg",
 	"/images/misc/sticky.gif": "sticky.svg",
 	"/images/misc/subscribed.gif": "subscribed.svg",
 	"/images/misc/trashcan_small.gif": "trashcan_small.svg",
	"/images/misc/whos_online.gif": "whos_online.svg",
	"/images/rating/rating_1.gif": "rating_1.svg",
	"/images/rating/rating_2.gif": "rating_2.svg",
	"/images/rating/rating_3.gif": "rating_3.svg",
	"/images/rating/rating_4.gif": "rating_4.svg",
	"/images/rating/rating_5.gif": "rating_5.svg",
	"/images/statusicon/forum_link.gif": "forum_link.svg",
	"/images/statusicon/forum_new.gif": "forum_new.svg",
	"/images/statusicon/forum_old.gif": "forum_old.svg",
	"/images/statusicon/post_new.gif": "post_new.svg",
	"/images/statusicon/post_old.gif": "post_old.svg",
	"/images/statusicon/subforum_new.gif": "subforum_new.svg",
	"/images/statusicon/subforum_old.gif": "subforum_old.svg",
 	"/images/statusicon/thread.gif": "thread.svg",
 	"/images/statusicon/thread_dot.gif": "thread_dot.svg",
 	"/images/statusicon/thread_dot_hot.gif": "thread_dot_hot.svg",
 	"/images/statusicon/thread_dot_hot_lock.gif": "thread_dot_hot_lock.svg",
 	"/images/statusicon/thread_dot_hot_lock_new.gif": "thread_dot_hot_lock_new.svg",
 	"/images/statusicon/thread_dot_hot_new.gif": "thread_dot_hot_new.svg",
 	"/images/statusicon/thread_dot_lock.gif": "thread_dot_lock.svg",
 	"/images/statusicon/thread_dot_lock_new.gif": "thread_dot_lock_new.svg",
 	"/images/statusicon/thread_dot_new.gif": "thread_dot_new.svg",
 	"/images/statusicon/thread_hot.gif": "thread_hot.svg",
 	"/images/statusicon/thread_hot_lock.gif": "thread_hot_lock.svg",
 	"/images/statusicon/thread_hot_lock_new.gif": "thread_hot_lock_new.svg",
 	"/images/statusicon/thread_hot_new.gif": "thread_hot_new.svg",
 	"/images/statusicon/thread_lock.gif": "thread_lock.svg",
 	"/images/statusicon/thread_lock_new.gif": "thread_lock_new.svg",
	"/images/statusicon/thread_moved.gif": "thread_moved.svg",
	"/images/statusicon/thread_moved_new.gif": "thread_moved_new.svg",
 	"/images/statusicon/thread_new.gif": "thread_new.svg",
	"/images/statusicon/user_offline.gif": "user_offline.svg",
	"/images/statusicon/user_online.gif": "user_online.svg",
};
Array.from(document.getElementsByTagName('img'))
	.filter(i => i.src.substr(0, 30) === "https://forums.alliedmods.net/")
	.forEach(i => { imageMap[i.src.substr(29)] && (i.src = "https://fennec.limetech.io/am-forum-svg/" + imageMap[i.src.substr(29)] + "?d=" + Date.now()); });
```
