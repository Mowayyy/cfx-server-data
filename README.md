# Windows

## Prerequisites

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
* Item 1
