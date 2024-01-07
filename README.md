# stepmania_sm_ssc_format
It is a self-note of StepMania ".SM" and ".SSC" format

# which format?
* .ssc is more modern and with more functionalities.
* .sm is the old format.

* If you still use Stepmania 3.x (why?), then .sm is your format
* Otherwise .ssc **(in case of doubt, use this one)**
* If you use both, then .ssc is the format used.
* There are other formats such as .ksf format but it is even older and it must not be used in any circumstances.

# differences
* .ssc has more tags but the form is similar excluding the notes.
.sm:
```
#NOTES:
     dance-single:
     desc:
     Easy:
     2:
     -1,-1,-1,-1,-1:
0000
0000
0000
0000
,
```

.ssc:
```
#NOTEDATA:;
#STEPSTYPE:dance-single;
#DESCRIPTION:desc;
#DIFFICULTY:Easy;
#METER:2;
#RADARVALUES:-1,-1,-1,-1;
#NOTES:
00000
00000
00000
00000
,
```

## types of notes
These are the standard note values:

* 0 – No note
* 1 – Normal note
* 2 – Hold head
* 3 – Hold/Roll tail
* 4 – Roll head
* M – Mine (or other negative note)
Later versions of StepMania accept other note values that may not work in older versions:
* K – Automatic keysound
* L – Lift note
* F – Fake note

# ssc
Copied from https://github.com/stepmania/stepmania/wiki/ssc

# Header Tags

Each TAG will have values that you can set/change. The format is as follows: TAG:VALUE; The value can be either a single line or span multiple lines. Just make sure it starts with : and ends with ;.

## \#VERSION

This is the version of the .ssc File Format.

## \#TITLE

**Sets the Song's Title.**  It is important.

## \#SUBTITLE

Sets the Song's Subtitle. (Optional)

## \#ARTIST

Sets the Song's Artist.

## \#TITLETRANSLIT

Sets the Song's Title Translation.

## \#SUBTITLETRANSLIT

Sets the Song's Subtitle Translation.

## \#ARTISTTRANSLIT

Sets the Song's Artist Translation.

## \#GENRE

Sets the Song's Genre.

## \#ORIGIN

Where the song came from if it's a crossover from an existing game.

No theme is known to use this, so it's essentially useless.

## \#CREDIT

Sets the .ssc Creator/Credits. Usually, the \#CREDIT tag in the note data is used instead.

## \#BANNER

Sets the path to the Banner. (Based on the current Song's directory.)

## \#BACKGROUND

Sets the path to the Background. (Based on the current Song's directory.)

## \#PREVIEWVID

Sets the path to the Preview Video. This is usually used in 'pump' based themes where there is a spot in the music select that plays the video. (Based on the current Song's directory.)

## \#JACKET

Sets the path to the Jacket. (Based on the current Song's directory.)

## \#CDIMAGE

Sets the path to the CD Image. (Based on the current Song's directory.)

## \#DISCIMAGE

Sets the path to the Disc Image. (Based on the current Song's directory.)

## \#LYRICSPATH

Sets the path to the [LRC](https://github.com/stepmania/stepmania/wiki/lrc) file containing the song's lyrics. (Based on the current Song's directory.)

## \#CDTITLE

Sets the Song's CD Title.

## \#MUSIC

Sets the path to the Song. (Based on the current Song's directory.)

## \#PREVIEW

Sets the path to a Preview file. If a valid preview file is set it will be played in the music wheel instead of the samplestart/samplelength defined for the song. (Based on the current Song's directory.)

## \#OFFSET

Sets the Song's Offset. (Effects the timing of the start of the NOTES.)

## \#SAMPLESTART

Sets when to play the song's sample when hovering over it in the music wheel.

## \#SAMPLELENGTH

Sets the Song's Sample Length.

## \#SELECTABLE

Allows or disallows the song from appearing in the music wheel. This is usually for a theme's tutorial song or other song not normally encountered during gameplay. (Values are `YES` or `NO`)

## \#BPMS

Sets the Song's Beats Per Minute's at certain times. (Can have multiple changes.)

## \#DISPLAYBPM
This can be used to override the BPM shown on ScreenSelectMusic. This tag supports three types of values:
 
* A number by itself (e.g. `#DISPLAYBPM:180;`) will show a static BPM.
* Two numbers in a range (e.g. `#DISPLAYBPM:90:270;`) will show a BPM that changes between two values.
* An asterisk (`#DISPLAYBPM:*;`) will show a BPM that randomly changes.

## \#STOPS

Sets the Song's Stops at certain times. (Can have multiple changes.)

## \#DELAYS

Sets the Song's Delays at certain times. (Can have multiple changes.)

## \#WARPS

Sets the Song's Warps at certain times. (Can have multiple changes.)

## \#TIMESIGNATURES

Sets the Song's Timing Signatures at certain times. (Can have multiple changes.)

## \#TICKCOUNTS

Sets the Song's checkpoint-hold tick count rate. (Can have multiple changes.)

## \#COMBOS

Sets the Song's Combo at certain times. (Can have multiple changes.)

## \#SPEEDS

Sets the Song's Rate(?) at certain times. (Can have multiple changes.)

## \#SCROLLS

(someone edit this section.)

## \#FAKES

Contains the Song's [Fake segments](https://github.com/stepmania/stepmania/wiki/Timing-Segments#fake). (Can have multiple Fake segments.)

## \#LABELS

Contains the Song's [Label segments](https://github.com/stepmania/stepmania/wiki/Label-segments). (Can have multiple Label segments.)

## \#LASTSECONDHINT

A float value. Tells StepMania when to end the song if your longest chart is shorter than this value. Normally song length is determined by the longest chart.
Required if your chart has only EDIT difficulties, as EDITs are not factored into song length calculation.

## \#BGCHANGES 

The BGCHANGES line is used to control what backgrounds are loaded by the simfile and when they appear. You can create, view, and modify BGChanges in the editor by pressing the `b` key while at the desired beat. 

For example, to view, edit, or create a BGChange at Beat = 25, navigate to beat 25 in the editor and press `b`.


An example BGCHANGES line in the ssc file might look like:
 
```
#BGCHANGES:0.000=springbn.png=1.000=1=0=1===CrossFade==;
```

Multiple background changes can be set by separating them with commas like:

```
#BGCHANGES:0.000=springbn.png=1.000=1=0=1===CrossFade==,
25.000=flash=1.000=0=0=1====#FFFFFF=;
```

The set of entries is between the colon and the semicolon.
Each entry is separated from the next by a comma.
Each entry is composed of 1 to 11 values separated by equals.
 
![image](https://user-images.githubusercontent.com/30600688/202782605-9bd6b076-31d4-4193-8d5e-43dd38e53d1a.png)

The meanings of the values are as follows:
 
1. start beat
2. file or folder name
3. play rate
4. Backward compatible transition type. CrossFade is used if this is not 0.
5. Backward compatible effect flag. StretchRewind is used if this is not 0.
6. Backward compatible effect flag. StretchNoLoop is used if this is not 0.
7. Name of the effect file to use. The BackgroundEffects folder will be searched for a match.
8. Name of the second file.
9. Name of the transition file to use. The BackgroundTransitions folder will be searched for a match.
10. Color string in either "1.0^0.5^0.75^0.25" or "#ff7fcf3f" form. The fourth channel is optional.
11. Second color string, same format.
 
The file names (values 2 and 8) and the colors (values 10 and 11) are passed to the effect file as thread variables.  Most effects do not use the second file.

TODO: Add more information about BGChanges in the editor

## \#KEYSOUNDS

Play a sound at a certain time, tied to a successful tap of a note or hold of a hold note.

Alternatively if you add a keysound in an empty row it will be converted to an AutoKeysound and will play automatically.

You can add keysounds using the editor.

The \#KEYSOUNDS tag is formatted like `#KEYSOUNDS:\bgm.wav,01.wav,02.wav,` (yes, the `\` is intentional, the tag is actually written like that.)

## \#ATTACKS

Sets the Song's Attacks. The syntax is identical to [how modifiers are applied in a course](https://github.com/stepmania/stepmania/wiki/Courses#mods).

# NOTE DATA

After these tags have been set, you can now start setting up the notedata. (Charts/Steps as StepMania would call it.)

All timing related tags can also be used in the notedata section. Combo, Tickcount, Attacks, keysounds, also works. #MUSIC also works in the notedata section allowing you to have different songs for each steps, although in multiplayer it will pick the master player's song.

\#DISPLAYBPM also seems to be supported in this section, but no theme displays per-chart BPMs.

## \#NOTEDATA

This tag has no value (#NOTEDATA:;) and represents the beginning of a note data section in the file.

## \#CHARTNAME

Sets this Chart's Name. ("Style - Difficulty" is the default/standard.)

## \#STEPSTYPE

Sets this Chart's Step Type. ("GameType-Style" is the default/standard.)

## \#DESCRIPTION

Describes this Chart's Type/Style/Difficulty.

## \#CHARTSTYLE

Sets this Chart's Style Custom Name.

## \#DIFFICULTY

Sets this Chart's Difficulty. Possible values are: `Beginner`/`Easy`/`Medium`/`Hard`/`Challenge`/`Edit`

## \#METER

Sets this Chart's Foot Meter, more commonly known as the difficulty level in other rhythm games.

The foot meter can be any number.

## \#RADARVALUES

Sets this Chart's Radar Values. Usually, these are automatically generated by the editor. (someone edit this section more.)

## \#CREDIT

Sets this Chart's Creators/Credits.

## \#NOTES

Sets this Chart's Notes.

## \#NOTES2

This tag is written instead of \#NOTES if you have keysounds in your ssc. Despite this, the ssc loader still loads it the same regardless of the tag.









