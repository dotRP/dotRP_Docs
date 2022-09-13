# MACH & Raven Functions  

Please read our [Documentation](https://docs.dotroleplay.com/mrfunctions) For help with configuration  

---

## Speed Limiter  

This allows you to set the max speed of each vehicle class, or set it to be unlimited.  
This is a hard cap which will stop the vehicle from being able to exceed that speed.  
[Speed Docs](https://docs.dotroleplay.com/mrfunctions/speed) ***caveats***.  

---

## Trains  

### Choo Choo  

This allows you to set if trains spawn and how often.  
There is not much more to it than that lol.  
[Train Docs](https://docs.dotroleplay.com/mrfunctions/trains)  

---

## Traffic  

This sets the multipliers for how many peds, cars etc are on the road.  
You will also be able to set if boats or garbage trucks spawn (TODO)  
[Traffic](https://docs.dotroleplay.com/mrfunctions/traffic)  

---

## DeadFinder

This allows you to set a key which wibbles your body when dead, this resets your location in the world.  
This is good for when bodies sometimes go missing when someone dies and EMS arrives  
[Dead Finder](https://docs.dotroleplay.com/mrfunctions/dead) ***caveats*** - Can trip some anticheat.  

---

---

### Code Commenting:  

This explains how the code is commented at the top of the config blocks  

FUNCTION NAME  
FILE (SEP)  
FILE LOCATION  
DEC (SEP)  
A SHORT DESCRIPTION  
IMPORTANT (SEP)  
ANY IMPORTANT INFO  
SUGGESTIONS (SEP)  
ANY SUGGESTED CONFIG  
INFO (SEP)  
ANY NATIVE INFO OR ODDITYS  

***Inline Comments***
**--Must be**
Must be a float! -- This means the number must have a decimal place, IE 1.0
Must be a INT! -- This means the number must be a whole number!
**--DEF** This is what the default recommended values are! /n
--DEF 300




```Lua
--SPEED LIMITER (THIS WILL BE THE Functions NAME)
--FILE
--client/Speed.lua (LOCATION OF FILE)
--Desc
--The sets the speedlimits for vechs (SHORT description)
--IMPORTANT
--this is based of the Vech class in <vehicleClass>xxxx</vehicleClass> in vehicles.meta, it does not care what is in your database! (ANY IMPORTANT INFO)
--Suggestion
--150 seems like a good max speed so far in testing, with 250 for heli/ac. You really dont want to be going much higher than this (ANY SUGGESTIONS)
--Info
--Car Class Info https://docs.fivem.net/natives/?_0x29439776AAA00A62 (ANY NATIVE INFO / ODDITIES )
--Some HUDS Round stuff weridly, so shown speed might be 1/2 MPH In either direction
--We also think that at very high speeds the math to caluclate it stuggles

```

---
