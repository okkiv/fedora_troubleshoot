# Problem:

- **LucidSound Wireless Headset has small volume range**
- **generally too loud, sound cutoff when volume slider ist moved too far to the left**

# Solution
### pipewire with pipewire-pulse (Fedora 34)
````
cd ~
mkdir -p .config/pipewire/media-session.d/
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
& **reboot**

### pipewire with wireplumber (Fedora 35)
````
cd ~
mkdir -p .config/wireplumber/main.lua.d/
cp /usr/share/wireplumber/main.lua.d/50-alsa-config.lua .config/wireplumber/main.lua.d/
nano .config/wireplumber/main.lua.d/50-alsa-config.lua
````

uncomment and change this line:
````
--["api.alsa.soft-mixer"] = false,
````
to this:
````
["api.alsa.soft-mixer"] = true,
````
& **reboot**
