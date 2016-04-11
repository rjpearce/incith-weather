incith:weather
===================
 - Retrieves weather and forecast data from 
 - www.wunderground.com
 - tested on Eggdrop v1.6.18

>This is a new git repo containing a copy of original
 incith-weather script written by Jordan.

> This repo has been setup to allow the community to make changes to the original code base, saving everyone the effort of manually having to apply the same fixes.

>Please help keep this script alive contact me for direct push permissions.

Usage
-----
      .chanset channel +weather
       !weather <search>
         returns the current conditions for the city found
       !forecast <search>
         returns a 3-day forecast for the city found
       !sky <location>
         returns the astronomy data for the city found

Forum Support
-------------
http://forum.egghelp.org/viewtopic.php?t=10466

ChangeLog:
-------------------
   

 - 2.0: script re-created.  more updates to come.
 - 2.1: 
	 - option for update time to be displayed in 24-hour (default)
	 - this removes AM/PM and the timezone if enabled
	 - more informative locations
	 - uses mobile.wunderground.com for forecast data if it has to
 - 2.2: fix for updated time.
 - 2.3:
	 - can use !w/!fc -set <location> to store a default, if you're an added member of the bots userlist (only way for now).
	 - small fix for updated time on some locations preventing results from being sent, igloolik was one such city.
 - 2.4:
	 - added new variable 'public_to_private' to control whether replies are sent to the channel or to the user requesting.
	- if it is set, the user will get /msg'd with the results, or they will get /notice'd if variable 'notices' is set to 1.
 - 2.5a:
	 - fixed high/low showing yesterdays data sometimes.. also if todays forecast is not available it will try mobiles.
 - 2.6:
	 - moved error checking higher up in fetch_html, fixes london.  
	 - convert EEST to EET to as Tcl does not recognize EEST (?) this fixes any location with EEST.
 - 2.6a: 
	 - there should never be a clock issue again as timezones are no longer being used in calculations, at all.
 - 2.7:
	 - astronomy is back, !sky <location>
	 - multiple results problem fixed (hull, united kingdom).
	 - variable weather_format controls which weather data's sent.
	 - forecast_format controls which forecast data's sent.
	 - pressure has been added back to !weather (%w9%).
	 - fixed a bug in the way i was grabbing wind direction basically, it wasn't showing 'Calm' when it actually was
	 - <country> searches (!w malaysia for example) will now return multiple results correctly.
	 - wunderground seems to have gone to a 3-day forecast for most locations, so I've modified the script accordingly.
	 - tries to fetch the current local time and date for accurate high/low display.
 - 2.7a: oops, small fix for 'unable to convert date time string'
 - 2.8: 
	 - fixed multiple results (especially !w india). this works now by stripping locations without temperatures no more 'cannot read (update_time)' in multiple results.
 - 2.8a: more multiple results fixes.
 - 2.8b: more multiple results fixes.  woot.
 - 2.8c: fixed conditions / location / todays_day / UV, and astronomy.
 - 2.8d: more fixes for forecast and location.                        
 - 2.8e: wunderground changed something that broke forecast; fixed.   
 - 2.8f:
	 - fixed a bug for the location 'unknown' and similar results.  
     - changed flood protection to ignore +f flagged users.
     - wunderground removed <nobr> tags breaking a lot of things.
     - fixed locations that have blank sunrise/sunset data.
 - 2.8g: removed <nobr> tags from html to fix things breaking again.  
 - 2.8h: fixed multiple results (they changed the layout).  again.    
 - 2.8i: it's not my fault, honest!  more multiple results fixes.     
 - 2.8j: fixes: temp, dew point, wind speed, better mobile backup.    
 - 2.8k: 
	 - added longitude & latitude back (optional, show_lat_lon var) 
     - major improvements to multiple results.
     - forecast will show the % chance of precipitation.
     - script was fetching mobile more often than it needed, fixed.
 - 2.8L: forecast modified for unknown change, capital L for LOLS!    
 - 2.8m: more small fixes and updates.                                 
 - 2.8n: windchill fix.                                               
 - 2.8o: they made units cookie based, fix to compensate.             
 - 2.8p: fix for public_to_private not working.                       
 - 2.8q: Correct missing celsius information, current weather only    
           returns farenheight. Script now converts on it's own.
 - 2.8r: Added "nickname" prefixes to commands optional. default is on
 - 2.9: Correct missing celsius info for dewpoint. same fix as temp. 
 - 2.9a: Corrected the way I was removing extraneous decimel points and ending 0's.
 - 2.9b: Corrected cruft within updated time.                         
 - 2.9c: Corrected multiple results.                            
 - 2.9d: Initial Refixed Version - There will be problems.            
 - 2.9e: Rollup of community fixes (use tls, switch to https)
 

Contact:
--------                                                   
   E-mail (incith@gmail.com) cleanups, ideas, bugs, etc., to me.     

TODO:
-----                                                      
   - locales for output (languages)                                  
   + fix multiple results, take best match, etc                      
 - merge _handlers, allow all %var% in all _formats, max_results
 - limit size of output, check length of variables?

LICENSE:
--------
>   This code comes with ABSOLUTELY NO WARRANTY.
   This program is free software; you can redistribute it and/or
   modify it under the terms of the GNU General Public License as
   published by the Free Software Foundation; either version 2 of
   the License, or (at your option) any later version.
   later version.
   This program is distributed in the hope that it will be useful,
   but WITHOUT ANY WARRANTY; without even the implied warranty of
   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
   See the GNU General Public License for more details.
   (http://www.gnu.org/copyleft/library.txt)

 Copyleft (C) 2005-10, Jordan
 incith@gmail.com (paypal donations accepted)
 irc.freenode.net / incith


