# perlink

Software Utility to choose browser on a per link basis.  
  
Tested to work on linux.
  
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
/home/<username>/.config/perlink/prefs.prefs.json  
```  
  
Modify it will reflect in the window options.  
Allowing you to pratically add to perlink any browser/software that can be launched via command line.
the contents of the file are in the format 
```
"name of button":"command to execute"
```
  
In order to link your already installed browser to a particular command if not already there:
```
touch firefox-beta
nano firefox-beta
```
paste in shell

```shell
#!/bin/sh
exec /path/to/your/browser/executable/browserexecutablename "$@"
```
save and then
```
chmod 777 firefox-beta
```
then move to any one of the folders listed in
```
$PATH
```
```
mv firefox-beta /destination/
```



Now running firefox-beta in terminal will open the browser you set up in the previous step

