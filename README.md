# Garry's Mod Egg
This Egg is the standard Garry's Mod Egg but it mounts Counter Strike Source automatically on installation


## What does it **add** to the default egg?

it only adds these lines to the installation script
```batch
## create dir for css content
mkdir -p /mnt/server/css_content

## install css content
./steamcmd.sh +force_install_dir /mnt/server/css_content +login ${STEAM_USER} ${STEAM_PASS} ${STEAM_AUTH} $( [[ "${WINDOWS_INSTALL}" == "1" ]] && printf %s '+@sSteamCmdForcePlatformType windows' ) +app_update 232330 validate +quit

## mount css content (add line to config)
sed -i '14 i \"cstrike\"    \"/home/container/css_content/cstrike\"' /mnt/server/garrysmod/cfg/mount.cfg
```

## What does it **change** in the default egg?

it adds a default password in the server.cfg and renames the server to "My cool Gmod Server" so that you can find it more easily.
```
hostname		"My cool Gmod Serve"
sv_password		"defaultpw"
```
