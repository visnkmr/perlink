# perlink

Software Utility to choose browser on a per link basis.  
  
Tested to work on  
✔️ Manjaro XFCE (Linux, based on Arch)  
✔️ Windows 11.
  
#### Setup:
1. Download the executable from the releases page.
2. Set the downloaded executable as default browser on your device.
  
  Features include 
  1. Open a link in all browsers at once,  
  2. expand a shortened URL before browsing it using any service of your choice, configurable in the config file mentioned below.  
  3. You can also Copy url to clipboard and open the app to select browser to open the url in. 
  4. You can use an extension in your browser to show url in window title and then open the app to select browser to open any of the open window url in.
  
![screenshot](https://github.com/visnkmr/perlink/raw/main/perlink_scr.png)
  
All browsers are opened using shell commands.  
  
🛠️ Rust with fltk frontend.

|Browser-name| command|
|-|-|
|Firefox| firefox|
|Vivaldi Stable | vivaldi-stable|
|Chromium| chromium|
|Firefox beta|firefox-beta|
|Firefox dev|firefox-dev|

Config file now stored @ 
```
Linux: /home/<username>/.config/perlink/config.toml  
Windows: Drive:\Users\username\AppData\Roaming\perlink\config.toml
```  
  
Modifying the config file will reflect in the window options.  
Allowing you to pratically add to perlink any browser/software that can be launched via command line.
the contents of the config file are in the format 
```
"name of button":"command to execute (should not have any arguments)"
```

In order add a button for your already installed browser just open config file and append this to config file before }}
```
Linux: "browsername":"/path/to/your/browser/executable"
Windows: "browsername":"Drive:/path/to/your/browser/executable"
```
You can check the [sample config](https://github.com/visnkmr/perlink/blob/main/sample-config.json) for a working implementation.
  
  
## Can be used:  
1. by Web developer to open website in all browsers with one click.  
2. to Open an already open browser window in another browser window using full link as title extension and our app, or ,Copy a link and open perlink to choose a browser to open the link in.
