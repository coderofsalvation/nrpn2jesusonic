nrpn2jesusonic
==============

Bash script which easily converts midi nrpn-descriptions into jesusonic plugins (to gain full midicontrol over your hardware mididevice).

Demo
====

<div><script id="playterm-MjAxMy0wNy9ucnBuMmplc3Vzb25pY3R0eXJlYy0xMzc1MjcxMTExfDgweDI0" type="text/javascript" src="http://playterm.org/js/?hash=MjAxMy0wNy9ucnBuMmplc3Vzb25pY3R0eXJlYy0xMzc1MjcxMTExfDgweDI0" class="size:80x24"></script></div>

What is jesusonic
=================
Jesusonic is the awesome AUDIO/MIDI plugin-scripting language made by cockos.
You can try it out by using their amazing DAW called [REAPER](http://reaper.fm) or
try their standalone VST 'reajs' which is available in the free [REAPLUGS VSTpack](http://www.reaper.fm/reaplugs)

Why this script
===============
Well Im a happy owner of the Korg Electribe ESX, and I wanted more control over my ESX. There's a great VST called 
DirectESX but I was looking for something more simple. At that point I was asking myself 'will I take the heroic task
 to write all NRPN-codes in a plugin'? Then the idea of generating it came into my mind, who knows people can reuse it with other NRPN-capable equipment.

Requirements
============
You need a machine which supports bash.

  * Windows: you will need to learn/download cygwin to run it
  * Linux: no problems, will run 
  * Mac: 99% sure since bash is shipped usually, but havent tested it

How it works
============
Well, basically you need to write- or get your hands on a textfile which describes the plugin:

    // channel, nrpn (decimal), name of slider
    0,1540,1-pitch/glide
    0,1547,1-pan
    0,1548,1-eg time
    .. and so on

Then the bashscript will parse every line into jesusonic code, which you can modify/alter by editing the files:

  * template.plugin (the master template) 
  * template.block  (piece of code what is generated for every slider)

Commandline invokation
======================

    ./nrpn2jesusonic example-electribe-esx.txt

or 
    
    ./nrpn2jesusonic example-electribe-esx.txt 19

The 19 indicates the max number of slider per plugin. (Thats right, if the txtfile is too big it can 
generate multiple plugins).

Thats it!

