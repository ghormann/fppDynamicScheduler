# FPP Dynamic Scheduler
This is a proposed plugin for FPP that would be an alternate scheduler for [FPP](https://github.com/FalconChristmas/fpp). 

## Features
* This scheduler is a "rule based" scheduler that periodically (default every 0.5 seconds) runs a check to decide which action to take next. (This means it can
  * Interrupting the currently playlist. (*Useful to start a specific playlist specifically at midnight on Christmas for instance.*) 
  * Dynamically adjust the order of future playlists based on internal input (MQTT, REST API). (*This can be used to have a voting website, have "push buttons" outside the display to select the next song.*)
  * Schedule specific playlists to run every xx minutes.  (*This might be useful if you have a donations reminder or some other bumper to run approximately every 10 minutes.*) 
* Allows for custom variables to be defined and tracked at both global and "per playlist" level (*example: "seconds since last played" (playlist level), "number of votes" (playlist level), "last time any bumper played" (global level), etc.*) 
* Leveraging the above variables, specific algorithms can run to adjust priority.While the plugin will ship with some rules, these rules can easily be expanded with custom Javascript. Based on these variables, specific algorithms can periodically run to adjust the priority of a specific playlist. 
* The publisher system can periodically publish information to both MQTT and REST API endpoints.  This information includes available playlists (useful for a voting website, current playlists and its duration, next scheduled playlists, overall scheduler health, and potentially more information in the future.) 

## Initial Constraints
* Like the default scheduler, this scheduler playlists and not sequences. This is mostly to allow for the flexibility the play list provides for doing pre-post tasks
* This scheduler will initially only allow for a single playlist to be running at a time. 


