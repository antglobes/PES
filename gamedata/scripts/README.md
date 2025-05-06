# Placeable Explosives

A Rework of Remote Controlled Explosives (RCE)

## Summary

This Addon is not only a rework of RCE but includes some additional features that work in
sync with the original features of RCE. Taking advanatage of Hideout Furniture's (HF)
placement system, Placeable Explosives (PES) piggybacks of that system allowing ied's
to be placed on any surface at any position. PES includes out of the box support for
[NERFS](https://www.moddb.com/mods/stalker-anomaly/addons/new-extensible-rf-sources) and [RRFR](https://www.moddb.com/mods/stalker-anomaly/addons/151152-coverdraves-reworked-rf-receiver-beeps) making it compatible if you have these mods installed. This addon
is standlone and is not compatible with RCE or any addon that edits the file `txr_mines.script`

## Functionality & Features

If you are more of a visual learner then there is a video that explains the functionality and features
with examples [here](https://www.youtube.com/watch?v=6YiryMg3PDw). If you prefer to read through alot of text feel free to carry on.

## Codepad UI

- Each placeable explosive has a codepad attached to it (Not on the model)
- It can be displayed by pressing the use key (by default F)
- Used for arming and disarming explosives and setting the mode

## Arming and Disarming

- To be able use the explosive it has to be armed
- A code via the codepad ui must be inputted to arm the explosive
- The Code has to:
  - Be within the current frequency range 30 - 300 (1 - 999 or whatever the max is set to if NERFS is installed)
  - If the code is below 100 it must start with a zero
  - If the code is below 10 it must start with 2 zeros
- By default if no mode is set and the code is valid then the explosive mode is set to remote
- The same code that was used to arm the explosive must be used to disarm it
- The Last digit of the code will be used to set the mode
  - e.g. 1680 = 168 + 0, 168 = 168 + 2, 030 = 30 + 2, 0301 = 30 + 1

## Explosive Modes

- There are 4 modes an explosive can be set to:
  - Value:Mode
  - 0.Proximity, 1:Timed, 2:Remote, 3:Pocket
- Proxmity:
  - A explosive set to this mode will detonate whenever an npc or the player (if not standing) enters it's trigger radius (MCM option)
  - A 5 second delay (MCM option) will be set after arming
  - If the player is crouched and within the trigger radius the explosive will not detonate
- Timed:
  - A explosive set to this mode will detonate after a certain delay (default is 10, MCM option)
  - If disarmed before that time is reached the explosive will not detonate
- Remote:
  - A explosive set to this mode will detonate whenever the trigger key (default is V, MCM option) is pressed
  - The code that the explosive is armed with, will be the frequency which triggers the detonation
  - If Multiple remote explosives are set to the same frequency, the explosives are detonated in order from most recently armed.
  - Explosives set in this mode can be picked up when armed, similarly to pocket explosives
- Pocket:
  - A explosive set to this mode will detonate after a preset time only when placed on an npc
  - Two options when planting either short or long (Both MCM Options)
  - Explosives set in this mode can be picked up when armed, similarly to remote explosives

## Pocket Planting

- There are 3 ways of pocket planting:
    1. Dialog Option
    2. Sneaky Planting
    3. Openly Giving
- For the latter 2 of the ways they are activated via the right click menu
- All 3 ways are only available if the explosive is set to remote or pocket mode
- Dialog Option:
  - Depending on your goodwill with the npc and it's faction
  - You can either lie about what you are giving the npc or tell the truth
  - The npc will react accordingly and either accept or refuse to take them
  - On some occasions the npc will realise that they have an explosive on them and attempt to disarm it (This also occurs with the Openly Giving method)
- Sneaky Planting
  - As long as the npc cannot see you
  - You can plant the explosive on their body
  - After a set amount of time they will recognise they have a bomb on them and remove it.
- Openly Giving
  - Works practically the same way as the Dialog Option
  - Except messages of their response will be sent via the news manager

## Remote Detonation

- As long as you ar within the max range (MCM Option)
- Holding the radio (RF Receiver)
- And are on a frequency that has explosives on remote mode set to
- Then press the trigger key
- The Last placed explosive in remote mode will detonate

## Future Implementation

- Defusing Minigame

## Changelog

- v1.0: Inital Upload. 06/05/25