### Helpers

**TODO**
```
	"/clear.gif": "/clear.svg",
	"/images/btn_donate_SM.gif": "/images/btn_donate_SM.svg",
	"/images/buttons/newthread.gif": "/images/buttons/newthread.svg",

buttons/collapse_generic
buttons/collapse_generic_collapsed

statusicon/user_invisible
misc/wol_error
misc/yellowcard_small
misc/yellowcard
misc/redcard_small
misc/redcard
misc/trashcan
misc/moderated
misc/moderated_small
misc/expires
statusicon/announcement_*
misc/menu_open_usercss

buttons/subscribe
buttons/viewpost
misc/calendar_icon
misc/birthday_small
misc/subscribed_event
misc/calendar
misc/progress
misc/lightbox_progress
buttons/sendtofriend
button/email
button/sendpm
button/home
button/find
misc/im_*
misc/11x11progress
poll/*
buttons/reputation
buttons/edit
buttons/forward
buttons/reply_small*
buttons/multiquote*
buttons/quickreply
gradients/gradient_tcat
reputation?/reputation_*
buttons/threadclosed
buttons/newthread
buttons/reply
buttons/printer
buttons/addpoll
buttons/mode_*
misc/tree_*
misc/question_icon
statusicon/wol_*
misc/userfield_edit

cross.png and tick.png used for registration errors, hardcoded into PHP
```

**Style Changes**
```
Add `margin: 0 10px;` to left forum icons on forum index.
.tcat .inlineimg { vertical-align: text-bottom; } AND the collapse_alt ones on PM page.
Add `vertical-align: baseline;` to lastpost image on right of forum index.
Adjust vertical-align of post header buttons (post_old, edit, quote, reply etc).
Add space between input box and calendar_popup.svg.
```

**Get All Images**
```
Array.from(document.getElementsByTagName("img"))
	.map(i => i.src)
	.filter(s => s.substr(0, 30) === "https://forums.alliedmods.net/")
	.map(s => s.substr(29))
	.filter((s, i, a) => a.indexOf(s) === i)
	.sort()
	.map(s => "\t\"" + s + "\": \"" + s.substr(0, s.length - 4) + ".svg\",")
	.reduce((r, s) => r + s + "\n", "\n");
```

**Image Mapping**
```
var imageMap = {
	"/images/buttons/collapse_alt.gif": "/images/buttons/collapse_alt.svg",
	"/images/buttons/collapse_alt_collapsed.gif": "/images/buttons/collapse_alt_collapsed.svg",
	"/images/buttons/collapse_tcat.gif": "/images/buttons/collapse_tcat.svg",
	"/images/buttons/collapse_tcat_collapsed.gif": "/images/buttons/collapse_tcat_collapsed.svg",
	"/images/buttons/collapse_thead.gif": "/images/buttons/collapse_thead.svg",
	"/images/buttons/collapse_thead_collapsed.gif": "/images/buttons/collapse_thead_collapsed.svg",
	"/images/buttons/firstnew.gif": "/images/buttons/firstnew.svg",
	"/images/buttons/infraction.gif": "/images/buttons/infraction.svg",
	"/images/buttons/ip.gif": "/images/buttons/ip.svg",
	"/images/buttons/lastpost.gif": "/images/buttons/lastpost.svg",
	"/images/buttons/nuke.gif": "/images/buttons/nuke.svg",
	"/images/buttons/report.gif": "/images/buttons/report.svg",
 	"/images/buttons/sortasc.gif": "/images/buttons/sortasc.svg",
 	"/images/buttons/sortdesc.gif": "/images/buttons/sortdesc.svg",
	"/images/buttons/unnuke.gif": "/images/buttons/unnuke.svg",
	"/images/misc/am-banner.png": "/images/misc/am-banner.svg",
	"/images/misc/birthday.gif": "/images/misc/birthday.svg",
	"/images/misc/calendar_popup.png": "/images/misc/calendar_popup.svg",
	"/images/misc/menu_open.gif": "/images/misc/menu_open.svg",
 	"/images/misc/multipage.gif": "/images/misc/multipage.svg",
 	"/images/misc/paperclip.gif": "/images/misc/paperclip.svg",
	"/images/misc/stats.gif": "/images/misc/stats.svg",
 	"/images/misc/sticky.gif": "/images/misc/sticky.svg",
 	"/images/misc/subscribed.gif": "/images/misc/subscribed.svg",
 	"/images/misc/trashcan_small.gif": "/images/misc/trashcan_small.svg",
	"/images/misc/whos_online.gif": "/images/misc/whos_online.svg",
	"/images/rating/rating_1.gif": "/images/rating/rating_1.svg",
	"/images/rating/rating_2.gif": "/images/rating/rating_2.svg",
	"/images/rating/rating_3.gif": "/images/rating/rating_3.svg",
	"/images/rating/rating_4.gif": "/images/rating/rating_4.svg",
	"/images/rating/rating_5.gif": "/images/rating/rating_5.svg",
	"/images/statusicon/forum_link.gif": "/images/statusicon/forum_link.svg",
	"/images/statusicon/forum_new.gif": "/images/statusicon/forum_new.svg",
	"/images/statusicon/forum_old.gif": "/images/statusicon/forum_old.svg",
	"/images/statusicon/pm_forwarded.gif": "/images/statusicon/pm_forwarded.svg",
	"/images/statusicon/pm_new.gif": "/images/statusicon/pm_new.svg",
	"/images/statusicon/pm_old.gif": "/images/statusicon/pm_old.svg",
	"/images/statusicon/pm_replied.gif": "/images/statusicon/pm_replied.svg",
	"/images/statusicon/post_new.gif": "/images/statusicon/post_new.svg",
	"/images/statusicon/post_old.gif": "/images/statusicon/post_old.svg",
	"/images/statusicon/subforum_link.gif": "/images/statusicon/subforum_link.svg",
	"/images/statusicon/subforum_new.gif": "/images/statusicon/subforum_new.svg",
	"/images/statusicon/subforum_old.gif": "/images/statusicon/subforum_old.svg",
 	"/images/statusicon/thread.gif": "/images/statusicon/thread.svg",
 	"/images/statusicon/thread_dot.gif": "/images/statusicon/thread_dot.svg",
 	"/images/statusicon/thread_dot_hot.gif": "/images/statusicon/thread_dot_hot.svg",
 	"/images/statusicon/thread_dot_hot_lock.gif": "/images/statusicon/thread_dot_hot_lock.svg",
 	"/images/statusicon/thread_dot_hot_lock_new.gif": "/images/statusicon/thread_dot_hot_lock_new.svg",
 	"/images/statusicon/thread_dot_hot_new.gif": "/images/statusicon/thread_dot_hot_new.svg",
 	"/images/statusicon/thread_dot_lock.gif": "/images/statusicon/thread_dot_lock.svg",
 	"/images/statusicon/thread_dot_lock_new.gif": "/images/statusicon/thread_dot_lock_new.svg",
 	"/images/statusicon/thread_dot_new.gif": "/images/statusicon/thread_dot_new.svg",
 	"/images/statusicon/thread_hot.gif": "/images/statusicon/thread_hot.svg",
 	"/images/statusicon/thread_hot_lock.gif": "/images/statusicon/thread_hot_lock.svg",
 	"/images/statusicon/thread_hot_lock_new.gif": "/images/statusicon/thread_hot_lock_new.svg",
 	"/images/statusicon/thread_hot_new.gif": "/images/statusicon/thread_hot_new.svg",
 	"/images/statusicon/thread_lock.gif": "/images/statusicon/thread_lock.svg",
 	"/images/statusicon/thread_lock_new.gif": "/images/statusicon/thread_lock_new.svg",
	"/images/statusicon/thread_moved.gif": "/images/statusicon/thread_moved.svg",
	"/images/statusicon/thread_moved_new.gif": "/images/statusicon/thread_moved_new.svg",
 	"/images/statusicon/thread_new.gif": "/images/statusicon/thread_new.svg",
	"/images/statusicon/user_offline.gif": "/images/statusicon/user_offline.svg",
	"/images/statusicon/user_online.gif": "/images/statusicon/user_online.svg",
};
Array.from(document.getElementsByTagName('img'))
	.filter(i => i.src.substr(0, 30) === "https://forums.alliedmods.net/")
	.forEach(i => { imageMap[i.src.substr(29)] && (i.src = "https://fennec.limetech.io/am-forum-svg" + imageMap[i.src.substr(29)] + "?d=" + Date.now()); });
```
