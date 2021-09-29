# Post install notes

### LucidSound Wireless Headset too loud, sound cutoff when volume slider ist moved too far to the left
````
cp /usr/share/pipewire/media-session.d/alsa-monitor.conf .config/pipewire/media-session.d/
nano .config/pipewire/media-session.d/alsa-monitor.conf
````

uncomment and change this line:
````
#api.alsa.soft-mixer = false
````
to this:
````
api.alsa.soft-mixer = true
````
