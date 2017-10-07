# BF4_SERVER_MONITOR

A standalone compact screen that connects to your home WiFi network and displays NWG BF4 server information in near-real time (refreshes every 30 seconds) using JSON feed from Battlelog live scoreboard.

Features:
- Displays key BF4 server information in near real-time.
- Web Control Panel - customize various setting through your browser, such as serverID, refresh interval, and display contrast.
- Ability to update firmware through your web browser (OTA), without the need for any special hardware tools. This provides flexibility for rolling out new features, or repurposing the unit for a totally different use.
- 3 spare GPIOs reserved for future hardware interfaces. 
- Dynamic WIFI Manager - creates WIFI Access Point to allow configuring to your home Wi-Fi network



Version History:
********* v1.2.30 (10/07/17) *********
- Introduced display ‘widgets’ concept. 
- Created weather forecast and current weather conditions widgets
- Added firmware auto-update engine (opt-out). Checks daily and within 5 minutes of power-up.
- Added display message upon failure to join WiFi network, instructing user to connect to AP to configure.
- Unit displays warning message not to power-off device during firmware update.
- Re-arranged Web Control Panel layout and added new content.
- Added auto-hide BF4 widget display is server empty option.

********* v1.2.01 (5/18/17) *********
- Enhanced error handling. Refresh 3 seconds after error. Also give WiFiClient 3 tries to connect before returning error code 2
- Prevent browser from caching Control Panel root page. 
- Added diagnostics page to Control Panel
- Expanded some game modes to 3 letters (TD->TDM, CF->CTF, DO->DOM)

********* v1.2 ******************
- Fixed new bug where Battlelog doesn't always immediately return 'Rush' info at round start.
- Cleaned up code (removed unsued files, organized DEFINEs)
- Fixed bug w/ EEPROM default values integrity check (upon FW flash).

********* v1.1 *****************
- Fixed rank divide by 0 bug [WEB_JSON_PARSE.ino]
- Password protected wifi configuratino portal (password = "NWG")
- Display firmware version # on web page
- Add display contrast config setting to web page (adjustable 1-100%)
- Swapped order in which destroyed & remaining MCOMs are drawn (blown up are now first)
- Fixed stability issues with WIFI client (improved error handling)
- Automatically save/load config settings to/from EEPROM (serverID, contrast, refresh)

********* v1.0  ****************
- Initial Release

Future Items:

[x] ADMIN TOOLS - SUSPICIOUS STATS ALERT
[BUG] proper contrast ratio conversion for web page
[x] Check web form refresh arg for overflow (or # digits)
[x] replace logo w/ instructions to connect to wifi manager 
[x] add wifi disconnected auto-restart ESP
[x] add Debug web page w/ SDK version, ESP SDK VERSION #, FREE HEAP, UPTIME, ETC.
[x] Graphics improvements:
	[x]	Icons for CTF/OB
	[x] Rush: highlight/outline current MCOM 
