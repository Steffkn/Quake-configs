Quake III Arena Point Release 1.32

--Index--
1 - Note to users
2 - PunkBuster implementation and funtionality
3 - What's changed



--- 

NOTE TO USERS PLANNING TO UNINSTALL OR REINSTALL QUAKE III, TEAM ARENA, ANY VERSION OF A POINT RELEASE: If you are planning to uninstall Quake III we STRONGLY recommend following these steps.

-         Remove any and all point releases from the Windows Control Panel Add/Remove Programs application. 

-         Remove Quake III Team Arena from the same application.

-         Remove Quake III from the same application.

-         Delete the Quake III Arena directory on your hard drive. 

 
Note:  If you install Quake 3: Team Arena after installing this point release, you will experience problems running the game.  If you wish to install Team Arena after applying the point release, please reinstall the download version of this point release after properly installing Team Arena (the auto-updater will not function in this situation, so you will need to have the downloaded point release file to properly install).  


If you run into ANY problems with Quake III and it’s point releases, we advise removing everything Quake III related on your system (see above for instructions), and starting from scratch. To reinstall the original versions of Quake III and Team Arena see (A). To reinstall the Ultimate Quake or Quake III: Gold versions of Quake III see (B).

 

(A)         Reinstall the game from the original disks, then download and install the 1.32 version of the point release. From this point, you will be able to check for updates by running the "Check for Quake III Arena Updates" program in your Windows start menu. We recommend using the Auto-Updater when updating Quake III. 

(B)         Reinstall the game from the original disks, then simply run “Check for Quake III Arena Updates” in the Quake III Arena folder in the Windows Start Menu.  

 
For a comprehensive list of what’s changed recently with Quake III Arena and Team Arena, please see the readme included with the 1.30 point release. This release is primarily a security release aimed a combating cheating.



---

A note on PunkBuster and how it works...

PunkBuster is an automatically self-updating Anti-Cheat software system. The PunkBuster system is designed to hold all participants accountable by scanning the game computers looking for known cheats, game hacks, and exploits similar to the way Anti-Virus software would scan a computer looking for a virus. PunkBuster is optional, however, without it you will not be able to play multiplayer on PunkBuster enabled servers.

When first installed, PunkBuster will be disabled. To enable PunkBuster so that you can join PunkBuster enabled servers, click 'Multiplayer' from the main menu. Find the clickable item in the upper right portion of the in-game server browser screen that says PunkBuster: Disabled and click it. If you have any problems getting PunkBuster enabled or any issues related to PunkBuster during gameplay, please visit <http://www.evenbalance.com> for support. The website contains documentation (including a FAQ), forums and contact information for email-based support.

----------------




CHANGES 1.32
8/26/2002

General:

- new network protocol, 68

- network code:
  improved fragmented messages handling
  map change while client loads map no longer causes an 'Invalid .PK3' error
  map_restart while client loads map no longer causes a reload
  fixing donedl being ignored after autodl if map_restart'ed
- the demo command has a list of compatible protocols, it will loop through 66 67 68
  you can do '/demo four' and it will try four.dm_66 four.dm_67 four.dm_68
  or you can explicitely give a '/demo demoname.dm_??'

- added mousewheel support in the console: 
  wheel to scroll, ctrl+wheel to scroll faster, shift+wheel to scroll history

- UI in baseq3/ and missionpack/ for PunkBuster configuration
  punkbuster server in server creation dialog (sv_punkbuster)
  punkbuster client in server browser (cl_punkbuster)
  added PB Yes/No to the browsers
- removed obsolete MPlayer UI stuff
- bumped server browser to handle up to 4096 servers

- IP maintained in userinfo
- cl_guid in userinfo (as part of PB integration)
- printing ports as unsigned ints, no longer printing negative port numbers
- cleaned up the legacy IP banning code
  use * for IP pattern matching now instead of 0 (fixes some confusion)
    ex: 192.246.12.*
  made it safe from overflowing and crashing
  NOTE: using PunkBuster's banning system is advised instead though
- rcon: some fixes to the buffering to avoid overflowing and dropping parts of the message 
- rcon: now supports quoting /rcon g_motd "foo bar"
- added SVF_CLIENTMASK (0x00000002), works only with <= 32 players
	set bitmask of players to which send entity
- pushed cl_maxpackets upper limit to 125
- added [skipnotify] from RTCW, use to display in the console only, but not on client screen
	(also fixes pb_msgprefix and pb_sv_msgprefix)

- new cvar sv_lanForceRate (defaults 1):
  forces LAN clients to the maximum rate instead of accepting client setting
  (1 is the default behaviour, backward compatible)

- new cvar sv_strictAuth (defaults 1):
  server side variable to control wether strict CDKEY auth should be performed with the auth server
  this is required if you want reliable cl_guid for the server (for users tracking)

- filesystem:
  client re-orders it's pk3s according to the order given by server
  (fixes some 'Invalid .PK3 files referenced' situations

- fixed invisible entities/players bug (thanks goes to Rick Johnson / Raven for this one!)
- update x86 VM code (better and safer optimisations) (Richk Johnson / Raven too)
- clearing client gentity before GAME_INIT call
- failing vote if there's only one voting client (fixes exploit on 2-player server where one player votes then disconnects, forcing vote to pass)

- added trap_FS_Seek

- renderer fix:
  if client game code registers a shader after drawsurfaces are generated but before frame is rendered
  had a one-frame visual glitch (shader indexes messed up)
- renderer fix:
  r_roundImagesDown 0 + map q3dm1 -> crash (buffer overflow fix)
- renderer fix:
  fixed a crash in widescreen displays (q3dm11)
- renderer fix:
  MAX_SHADERS up to 2^12  
- renderer fix:
  moved screenshot from frontend to backend, fixes broken r_smp 1 screenshots

- TA fixes:
  MOD_KAMIKAZE MOD_JUICED logging properly to games.log
  fixed bot taunt spamming
- fixed typo in scripts/models2.shader (shader error Ursula head)

Win32 specific:

- fixed the DirectInput mouse init procedure
- rcon:
  fixed rcon not working on NT/2000/XP workstations that have a long uptime

Linux specific:

- no longer trying to load libMesaVoodooGL.so
  obsolete code, was confusing when trying to setup correct OpenGL acceleration
- SMP support in the renderer. Detects CPU count, r_smp 1 default if available. (thanks to Gareth Hughes for contributing this)
- changed default GL driver from libGL.so to libGL.so.1
  see LSB 1.2 spec: http://www.linuxbase.org/spec/refspecs/LSB_1.2.0/gLSB/libgl.html
- Handle Ctrl and Space key together correctly (Ctrl was disabling Space)    
- sub-frame timing of input events (key/mouse) (input timing quality now equivalent to win32)


-------------------------------------


12-14-01 - Notable Changes and What’s New
 

Windows Fixes:

- fixed Doppler effect
- changed protocol from 66 to 67
- fixed simple developer 1 cvar cheat hack
- changed a few warnings to developer warnings
- rcon commands no longer fragment, sent buffered to the rcon client
- fixed connection issues / broken userinfo
- only printing R_AddPolyToScene warnings with +set developer 1
- various dedicated server issues fixed 

 
Linux only:
- fixed sound crash, going around memset bug in glibc i586/i686

 



