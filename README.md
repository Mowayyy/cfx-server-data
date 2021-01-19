## Windows

### Prerequisites

1. First step [artifacts-fivem-windows](https://github.com/Mowayyy/artifacts-fivem-windows)
2. [Visual C++ Redistributable 2019](https://aka.ms/vs/16/release/VC_redist.x64.exe) or newer.
3. [Git](https://git-scm.com/download/win) to assure a correct installation.

### Installation

1. Clone [cfx-server-data](https://github.com/citizenfx/cfx-server-data) in a new folder outside of your server binaries folder, for example, `D:\FXServer\server-data`.
4b. `git clone https://github.com/citizenfx/cfx-server-data.git server-data`
2. Make a server.cfg file in your `server-data` folder (copy the example server.cfg file below into that file).
3. Set the license key in your server.cfg using `sv_licenseKey "licenseKeyGoesHere"`.
4. Run the server from the `server-data` folder. For example, in a plain Windows command prompt (cmd.exe) window:
```
cd /d D:\FXServer\server-data
D:\FXServer\server\FXServer.exe +exec server.cfg
```
(the /d flag is only needed when changing directory to somewhere on a different drive)

# Linux

## Prerequisites

1. First step [artifacts-fivem-linux](https://github.com/Mowayyy/artifacts-fivem-linux)

### Installation

1. Clone [cfx-server-data](https://github.com/citizenfx/cfx-server-data) in a new folder outside of your server binaries folder.
4b. For example `git clone https://github.com/citizenfx/cfx-server-data.git /home/username/FXServer/server-data`
2. Make a **server.cfg** file in your server-data folder (copy the example server.cfg file below into that file).
3. Set the license key in your `server.cfg` using `sv_licenseKey "licenseKeyGoesHere"`.
4. Run the server from the `server-data` folder.
7b. `bash /home/username/FXServer/server/run.sh +exec server.cfg`

### Common issues

* If you don't get any 'resources found', and it says 'Failed to start resource', you didn't 'cd' to the right folder.
* If no resources get started, and you can't connect, you didn't add +exec.
* If you get 'no license key was specified', one of the above things applies.

# server.cfg

```
# Only change the IP if you're using a server with multiple network interfaces, otherwise change the port only.
endpoint_add_tcp "0.0.0.0:30120"
endpoint_add_udp "0.0.0.0:30120"

# These resources will start by default.
ensure mapmanager
ensure chat
ensure spawnmanager
ensure sessionmanager
ensure basic-gamemode
ensure hardcap
ensure rconlog

# This allows players to use scripthook-based plugins such as the legacy Lambda Menu.
# Set this to 1 to allow scripthook. Do note that this does _not_ guarantee players won't be able to use external plugins.
sv_scriptHookAllowed 0

# Uncomment this and set a password to enable RCON. Make sure to change the password - it should look like rcon_password "YOURPASSWORD"
#rcon_password ""

# A comma-separated list of tags for your server.
# For example:
# - sets tags "drifting, cars, racing"
# Or:
# - sets tags "roleplay, military, tanks"
sets tags "default"

# A valid locale identifier for your server's primary language.
# For example "en-US", "fr-CA", "nl-NL", "de-DE", "en-GB", "pt-BR"
sets locale "root-AQ" 
# please DO replace root-AQ on the line ABOVE with a real language! :)

# Set an optional server info and connecting banner image url.
# Size doesn't matter, any banner sized image will be fine.
#sets banner_detail "https://url.to/image.png"
#sets banner_connecting "https://url.to/image.png"

# Set your server's hostname
sv_hostname "FXServer, but unconfigured"

# Nested configs!
#exec server_internal.cfg

# Loading a server icon (96x96 PNG file)
#load_server_icon myLogo.png

# convars which can be used in scripts
set temp_convar "hey world!"

# Remove the `#` from the below line if you do not want your server to be listed in the server browser.
# Do not edit it if you *do* want your server listed.
#sv_master1 ""

# Add system admins
add_ace group.admin command allow # allow all commands
add_ace group.admin command.quit deny # but don't allow quit
add_principal identifier.fivem:1 group.admin # add the admin to the group

# enable OneSync (required for server-side state awareness)
set onesync on

# Server player slot limit (see https://fivem.net/server-hosting for limits)
sv_maxclients 48

# Steam Web API key, if you want to use Steam authentication (https://steamcommunity.com/dev/apikey)
# -> replace "" with the key
set steam_webApiKey ""

# License key for your server (https://keymaster.fivem.net)
sv_licenseKey changeme
```
