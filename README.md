### Helpers

**TODO**
```
btn_donate_SM.gif

statusicon/wol_*
misc/question_icon

button/email
button/find
button/home
button/sendpm
buttons/addpoll
buttons/edit
buttons/forward
buttons/mode_*
buttons/multiquote*
buttons/newthread
buttons/printer
buttons/quickreply
buttons/reply
buttons/reply_small*
buttons/reputation
buttons/sendtofriend
buttons/subscribe
buttons/threadclosed
gradients/gradient_tcat
misc/11x11progress
misc/birthday_small
misc/calendar
misc/calendar_icon
misc/im_*
misc/lightbox_progress
misc/progress
misc/subscribed_event
misc/tree_*
poll/*
reputation?/reputation_*

Still need to figure out how to implement calendar_popup, it is added in JS.

cross.png and tick.png used for registration errors, hardcoded into PHP
```

**Style Changes**
```
Adjust vertical-align of post header buttons (post_old, edit, quote, reply etc).
Add space between input box and calendar_popup.svg.
remove inlineimg from quote (viewpost.svg)
the large infraction cards are now used on the profile, change postbit to use small which can then be made whatever size fits nicely
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
	"/images/buttons/collapse_generic.gif": "/images/buttons/collapse_generic.svg",
	"/images/buttons/collapse_generic_collapsed.gif": "/images/buttons/collapse_generic_collapsed.svg",
	"/images/buttons/collapse_tcat.gif": "/images/buttons/collapse_tcat.svg",
	"/images/buttons/collapse_tcat_collapsed.gif": "/images/buttons/collapse_tcat_collapsed.svg",
	"/images/buttons/collapse_thead.gif": "/images/buttons/collapse_thead.svg",
	"/images/buttons/collapse_thead_collapsed.gif": "/images/buttons/collapse_thead_collapsed.svg",
	"/images/buttons/firstnew.gif": "/images/buttons/firstnew.svg",
	"/images/buttons/infraction.gif": "/images/buttons/infraction.svg",
	"/images/buttons/ip.gif": "/images/buttons/ip.svg",
	"/images/buttons/lastpost.gif": "/images/buttons/lastpost.svg",
	"/images/buttons/nuke.gif": "/images/buttons/nuke.svg",
	"/images/buttons/redcard.gif": "/images/buttons/redcard.svg",
	"/images/buttons/report.gif": "/images/buttons/report.svg",
 	"/images/buttons/sortasc.gif": "/images/buttons/sortasc.svg",
 	"/images/buttons/sortdesc.gif": "/images/buttons/sortdesc.svg",
	"/images/buttons/unnuke.gif": "/images/buttons/unnuke.svg",
	"/images/buttons/viewpost.gif": "/images/buttons/viewpost.svg",
	"/images/buttons/yellowcard.gif": "/images/buttons/yellowcard.svg",
	"/images/misc/am-banner.png": "/images/misc/am-banner.svg",
	"/images/misc/birthday.gif": "/images/misc/birthday.svg",
	"/images/misc/calendar_popup.png": "/images/misc/calendar_popup.svg",
	"/images/misc/expires.gif": "/images/misc/expires.svg",
	"/images/misc/menu_open.gif": "/images/misc/menu_open.svg",
	"/images/misc/menu_open_usercss.gif": "/images/misc/menu_open_usercss.svg",
 	"/images/misc/moderated.gif": "/images/misc/moderated.svg",
 	"/images/misc/moderated_small.gif": "/images/misc/moderated_small.svg",
 	"/images/misc/multipage.gif": "/images/misc/multipage.svg",
 	"/images/misc/paperclip.gif": "/images/misc/paperclip.svg",
 	"/images/misc/redcard_small.gif": "/images/misc/redcard_small.svg",
	"/images/misc/stats.gif": "/images/misc/stats.svg",
 	"/images/misc/sticky.gif": "/images/misc/sticky.svg",
 	"/images/misc/subscribed.gif": "/images/misc/subscribed.svg",
 	"/images/misc/trashcan.gif": "/images/misc/trashcan.svg",
 	"/images/misc/trashcan_small.gif": "/images/misc/trashcan_small.svg",
 	"/images/misc/userfield_edit.gif": "/images/misc/userfield_edit.svg",
	"/images/misc/whos_online.gif": "/images/misc/whos_online.svg",
	"/images/misc/yellowcard_small.gif": "/images/misc/yellowcard_small.svg",
	"/images/rating/rating_1.gif": "/images/rating/rating_1.svg",
	"/images/rating/rating_2.gif": "/images/rating/rating_2.svg",
	"/images/rating/rating_3.gif": "/images/rating/rating_3.svg",
	"/images/rating/rating_4.gif": "/images/rating/rating_4.svg",
	"/images/rating/rating_5.gif": "/images/rating/rating_5.svg",
	"/images/statusicon/announcement_new.gif": "/images/statusicon/announcement_new.svg",
	"/images/statusicon/announcement_old.gif": "/images/statusicon/announcement_old.svg",
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
	"/images/statusicon/user_invisible.gif": "/images/statusicon/user_invisible.svg",
	"/images/statusicon/user_offline.gif": "/images/statusicon/user_offline.svg",
	"/images/statusicon/user_online.gif": "/images/statusicon/user_online.svg",
	"/images/statusicon/wol_error.gif": "/images/statusicon/wol_error.svg",
};
Array.from(document.getElementsByTagName('img'))
	.filter(i => i.src.substr(0, 30) === "https://forums.alliedmods.net/")
	.forEach(i => { imageMap[i.src.substr(29)] && (i.src = "https://fennec.limetech.io/am-forum-svg" + imageMap[i.src.substr(29)] + "?d=" + Date.now()); });
```
