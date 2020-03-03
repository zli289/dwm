#	dwm - dynamic window manager
dwm is an extremely fast, small, and dynamic window manager for X.


#	Requirements
In order to build dwm you need the Xlib header files.

Change config.mk file.
```
X11INC = /usr/include/X11
X11LIB = /usr/lib/X11
```

#	Installation
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):
```
make clean install
```

#	Patches
+	dwm-alpha-20180613-b69c870.diff
+	dwm-autostart-20161205-bb3bd6f.diff
+	dwm-awesomebar-20191003-80e2a76.diff
+	dwm-fibonacci-5.8.2.diff
+	dwm-fullscreen-6.2.diff
+	dwm-hide_vacant_tags-6.2.diff
+	dwm-noborder-6.2.diff
+	dwm-rotatestack-20161021-ab9571b.diff
+	dwm-vanitygaps-20190508-6.2.diff

#	Running dwm
Add the following line to your .xinitrc to start dwm using startx:
```
exec dwm
```
In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:
```
DISPLAY=foo.bar:1 exec dwm
```
(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:
```
while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
do
	sleep 1
done &
exec dwm
```

#	Configuration
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
