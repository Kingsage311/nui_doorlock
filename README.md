<h3 align='center'>For more support or to see more of my resources you can join my <a href='https://discord.gg/hmcmv3P7YW'>discord</a></h3>

# <a href='https://forum.cfx.re/t/esx-nui-doorlock-improved-performance-supports-sliding-doors/2068259'>nui_doorlock</a>
A fork of esx_doorlock, featuring improved performance and improved functionality.
<p align="center"><img src="https://i.imgur.com/2Yz7Rtm.png"/></p>
<hr>

* Easily add and configure new doors!  
Use the /newdoor command to automatically create a new entry on the DoorList.  
https://streamable.com/e290wk  
Try using `con_miniconChannels script:nui_doorlock` for errors to popup

* No more `SetEntityHeading` and `FreezeEntityPosition` natives.  
 Doors in range are assigned a doorHash, used with `AddDoorToSystem`.  
 Doors are assigned a state depending on if they are unlocked, locked, or locking with `DoorSystemSetDoorState`.  

* Garage doors and gates can be locked and will properly move into the correct position.  
If a player comes into range of an unlocked automatic door like this, it will open appropriately.  

* The state of the door is drawn into the world using NUI, meaning full customisation of the appearance and content.  
By default, icons from font-awesome are being displayed; but there is support for images with this method.  
Customisable sound playback! Modify the lock and unlock sound on a door-by-door basic.  

* Improved performance by utilising threads and functions where appropriate.  
Instead of updating the door list every X seconds, your position will be compared to where the last update occured and update when appropriate.  
The state of doors is only checked while in range, and the number of checks per loop depends on the state of the door.  

* Persistent door states! Door states are saved when the resource stops, then loaded back up on start.  
States.json will auto-generate if the file does not exist.  
When adding new doors to the config, you should delete states.json so a new one can be made.

* Config for both Community MRPD and gabz_MRPD  
Just choose which config file to use and rename if using gabz.

* Set door access permissions  
Set multiple jobs to be authorised to use a door `authorizedJobs = { 'police', 'offpolice' }`  
Set the minimum rank for using a door `minimumRank = {['police']=1, ['offpolice']=1}`

<hr>
<p align="center">https://streamable.com/oheu5e  
<img src="https://i.imgur.com/Sug2Nj5.jpg"/></p>


<hr>

<br><br><br>
<p align="center">Original</p>

# esx_doorlock
This is a door lock script for ESX, which is used to lock certain doors that shouldn't be accessable by normal citizens.

This script was originally developed by Darklandz, later modified by Miss_Behavin and others.

### Features
- Well optimized script
- Supports mutliple jobs for each door

## Download & Installation

### Using [fvm](https://github.com/qlaffont/fvm-installer)
```
fvm install --save --folder=esx esx-public/esx_doorlock
```

### Using Git
```
cd resources
git clone https://github.com/ESX-PUBLIC/esx_doorlock [esx]/esx_doorlock
```

### Manually
- Download https://github.com/ESX-PUBLIC/esx_doorlock/archive/master.zip
- Put it in the `[esx]` directory

## Installation
- Add this to your `server.cfg`:

```
start esx_doorlock
```

# Legal
### License
esx_doorlock - door locks for ESX

Copyright (C) 2015-2018 ElPumpo / Hawaii_Beach

This program Is free software: you can redistribute it And/Or modify it under the terms Of the GNU General Public License As published by the Free Software Foundation, either version 3 Of the License, Or (at your option) any later version.

This program Is distributed In the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty Of MERCHANTABILITY Or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License For more details.

You should have received a copy Of the GNU General Public License along with this program. If Not, see http://www.gnu.org/licenses/.
