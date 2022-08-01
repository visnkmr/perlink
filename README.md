# perlink

A software to choose browser on a per link basis.  
All browsers are opened using command line arguments.  
  
Made using Rust with fltk frontend.

|Browser-name| command|
|-|-|
|Firefox| firefox|
|Vivaldi Stable | vivaldi-stable|
|Chromium| chromium|
|Firefox beta|firefox-beta|
|Firefox dev|firefox-dev|

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

