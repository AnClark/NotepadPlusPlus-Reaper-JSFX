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

## Known issues
#### I. Description lines
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

#### II. `/*` symbol in `provides:` line
Some JSFX scripts use `provides:` description line. It can use filename wildcards such as "\*", and split parameters with a "/". So there often be a `/*` in `provides:` line. Official hasn't explained this usage yet. As we know, currently when UDL meets `/*`, it usually consider it as a block comment. 

For example, this code section:
```
provides: TiaR_2op PM Synth/*
link: http://forum.cockos.com/showthread.php?p=1385314&posted=1#post1385314

//PMX - 2op PM synth with crazy feedback  (x3 with detune for fatness)
//_____________________________________________________________________
slider1:<0,11,1{Mono,Mono 8ct,Mono 5th,Stereo,Stereo 8ct,Stereo 5th,All Mono,All Mono 8ct,All Mono 5th,All Stereo,All Stereo 8ct,All Stereo 5th}>Mix Type

slider3:0<0.001,10>--1 A
slider4:0.3<0.001,10>--1 D
slider5:0.5<0,1>--1 S
slider6:0.7<0.001,10>--1 R
......
```
Sections after `/*` will be treated as a block comment, even though they are truly codes.

## Developer
Developed by AnClark Liu \<anclarkliu@outlook.com\>, a musician and programmer using REAPER.

## References
- [REAPER Official JSFX Programming Documents](https://www.reaper.fm/sdk/js/js.php)


