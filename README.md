# NotepadPlusPlus Reaper JSFX
## Introduction
This is a Notepad++ syntax highlight solution of REAPER Jesusonic Effects (JSFX) scripts. Created with User Defined Language (UDL). It can give you some basic highlight supports if you would program or view JSFX with Notepad++.

**JSFX**, fully called **Jesusonic Effects**, is an EEL-based programming language developed by Cockos Incorporated. It allows you to control / modify audio and MIDI in the REAPER DAW. You can use this language to write audio or MIDI (even video!) plugins, and have so much fun.

## Features
- Basic keyword highlighting
- Bolden operators
- Highlight bulit-in essential functions separately
- Highlight some special variables, methods and functions introduced in the official document (e.g. GFX methods)

## How to use
- Download the UDL file `AnClark_UserDefinedLanguage_JSFX.xml` in this repository;
- Pick the `Define your language...` menu item from the "Language" menu;
- Click the `Import...` button, then choose the UDL file above;
- Now everything is OK, just open a JSFX file, and pick `Jesusonic Effects`from the "Language" menu. Then your script will be highlighted!

### Notice: 
REAPER's JSFX files usually have no suffix. You may have to manually enable highlighting through the "Language" menu.

## Known issue
UDL cannot handle JSFX's description lines well. Here is an example of description lines:

```
desc:3-Band EQ
desc:3-Band EQ [LOSER]

slider1:0<-24,24,1>Low (dB)
slider2:200<0,22000,1>Frequency (Hz)
slider3:0<-24,24,1>Mid (dB)
slider4:2000<0,22000,1>Frequency (Hz)
slider5:0<-24,24,1>High (dB)
slider6:0<-24,24,1>Output (dB)
```

Normally, it should be parsed as plain text (just like a comment) after colon or ">" (for `slider` description which has a complex syntex). That means any keywords appearing after colon or ">" should not be highlighted. But currently UDL cannot handle this requirement.

## Developer
Developed by AnClark Liu \<anclarkliu@outlook.com\>, a musician and programmer using REAPER.

## References
- [REAPER Official JSFX Programming Documents](https://www.reaper.fm/sdk/js/js.php)


