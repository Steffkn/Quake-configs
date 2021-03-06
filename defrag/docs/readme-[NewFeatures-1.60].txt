* history 1.70 *

- Included CPM Defrag
- CPM: Added CPM Air Control and bunny
- CPM: Added Ramp-Jump and Double Jump
- CPM: Added CPM under-water movements
- CPM: Added CPM weapon settings
- Added CPM bugs fix for Id Software code
- Stats tracked and displayed in the console at end of run
- New conversion table for the Speed Meter accuracy
- Id Software code ported from 1.27 to 1.29h
- Hud: Added height meter (/df_drawHeight)
- Hud: Added jump distance meter (/df_drawDistance)
- Hud: Added crosshair health/armor display for faster reading (/df_drawCrosshairStats)
- Hud: Added crosshair speed display for faster reading (/df_drawCrosshairSpeed)
- Hud: Added animated life icon
- Hud: Added custom colors CVars (/df_hud_colorRGB /df_hud_fontcolorRGB)
- Hud: Fixed powerups display bug
- Hud: Fixed checkpoints display possible problem
- Autorecord: /df_name contains player name, specifically used for demo naming
- Autorecord: g_synchronousClients 0 compatibility
- Autorecord: timer-reset don't restart recording until 30s have passed since last time
- Autorecord: Fixed bug occuring when /name contains spaces
- Cheat Protection: Bsp Checksum verification
- Cheat Protection: Strengthened timer encryption with in-game variable factors
- Cheat Protection: Forbidden sv_fps/com_maxFps values reported so to prevent from looped sv_fps/com_maxFps commands cheat
- Cheat Protection: Fixed bug occuring at auth process
- UI: Registration limits extended for maps(x4) and demos(x2)
- UI: 15 maps displayed per menu page
- UI: Menu got bunnies invaded
- Mapping: Added Silent option to fragsfilters (disables frags-warning messages)
- Mapping: Added Reset option to fragsfilters (resets player score to 0)
- Mapping: Removed Runonce option from fragsfilters (now set on by default)
- Checkpoints displayed while playing demos
- Removed Powerups respawn sound
- Newly performed best time and checkpoints no more kept on Hud when cheats are enabled
