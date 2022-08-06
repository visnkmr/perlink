# perlink

Software Utility to choose browser on a per link basis.  
  
Tested to work on Manjaro XFCE (Linux, based on Arch), Windows 11.
  
  Features include Open a link in all browsers at once, expand a shortened URL before browsing it.
  
![screenshot](https://github.com/visnkmr/perlink/raw/main/perlink_scr.png)
  
All browsers are opened using shell commands.  
  
Made using Rust with fltk frontend.

|Browser-name| command|
|-|-|
|Firefox| firefox|
|Vivaldi Stable | vivaldi-stable|
|Chromium| chromium|
|Firefox beta|firefox-beta|
|Firefox dev|firefox-dev|

Config file now stored @ 
```
Linux: /home/<username>/.config/perlink/config.json  
Windows: Drive:/Users/username/AppData/Roaming/perlink/
```  
  
Modify it will reflect in the window options.  
Allowing you to pratically add to perlink any browser/software that can be launched via command line.
the contents of the file are in the format 
```
"name of button":"command to execute"
```

In order add a button for your already installed browser just open config file and append this to config file before }}
```
"browsername":"exec //path//to//your//browser//executable//browserexecutablename"
```
You can check the [sample config](https://github.com/visnkmr/perlink/blob/main/sample-config.json) for a working implementation.

