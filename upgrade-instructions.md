---
nav-title: Upgrade instructions
title: "Upgrade instructions"
description: Upgrade instructions
position: 20
---

# Upgrade Instructions

### Upgrading the NativeScript Tools

First thing to do is upgrade your TNS (or NativeScript) command, so go to a command prompt or bash/terminal prompt and type:
```
npm update -g nativescript
```

This will update you to the latest version of the nativescript command line.  
You can type **tns --version** to verify new version is installed.

### Upgrading the Platforms

Next thing you will need to upgrade is your **platforms**, so navigate to the root level folder where your project is; and then if you are working on a Android project type:
```
tns platform update android
```

and/or (if you are working on a iOS version on a Macintosh):
```
tns platform update ios
```

### Upgrading TNS Modules

Unfortunately the next piece is a bit more tricky as it requires more steps. The easiest method is to create a new project and then copy the **tns_modules** out of the new project into your existing project and then delete the dummy project.

So at a command line do the following (assuming you are still in your main app project folder from the steps above). Please remember to replace **<yourapp>** with whatever folder name your app is in.

Windows:
```
cd ..
tns create TempApp
rd /S /Q **<yourapp>**\app\tns_modules
move TempApp\app\tns_modules **<yourapp>**\app
rd /S /Q TempApp
```

Linux/Macintosh:
```
cd ..
tns create TempApp
rm -rf **<yourapp>**/app/tns_modules
mv TempApp/app/tns_modules **<yourapp>**/app
rm -rf TempApp
```