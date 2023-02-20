---
id: MachsVedning
---

# Machs Vending [ESX]  

[![GitHub version](https://badge.fury.io/gh/dotRP%2FdotRP_VersionTracking.svg)](https://badge.fury.io/gh/dotRP%2FdotRP_VersionTracking)  

## UNDER CONSTRUCTION  

Please read our [Documentation](https://docs.dotroleplay.com/machsvending) For help with configuration  

![image](https://docs.dotroleplay.com/machsvendingheader.png)

---

[Get it on tebex - TODO](https://store.dotroleplay.com/) - NOT YET FOR SAKE

## Description  

Introducing Machs Vending, a ESX Based job script for FiveM! This script is perfect for those looking to add more dynamic and interactive jobs to their servers.  
Using QTarget* you can now offer your players the opportunity to become Vending Machine Operators, interacting with customers and restocking machines throughout the city.  

This script allows your players to manage company inventory, restock machines, and collect payments with ease. It's a perfect addition to any economy-based server, as players can earn money by selling a variety of snacks and drinks to thirsty citizens. The script is easy to install and can be customized to suit the needs of your server.  

Our Vending Machine job script is a great way to add a unique and engaging job for your players, and give them an opportunity to make money in a fun and interactive way. With the script, your players can become entrepreneurs, managing their own vending machine empire and building their reputation throughout the city.

> Generated the ***DESCRIPTION*** In chatGPT and then cleaned it up. Because I am terrible with words.  
> "*" I Believe the script should be drop in replaceable with OX_Target, however this is untested and will require YOU To modify the script  

## Features

- Stock System - Each Machine tracks stock of each item within it and can be refilled by a person with the right job.
- Self Initializing - No more adding 1000 entries into the database, this does it itself on the first use.  
- Tax - Take an amount per item and have it go into a separate tax box in each machine
- Cash - The money needs to be collected from each machine  
- Low Stock Blips
- From the job menu or boss pc, get the locations of all machines with a low stock to show on your map  
- Works out the box with the ***Default*** GTA Vending props: Coffee Machine, Fixed Coffee Carts , Sprunk & Cola, Snacks, Raine Water, Slush Machines and most water coolers

## Video  

<iframe width="560" height="315" src="https://www.youtube.com/embed/DId1UYTBmBM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>  

---

## Requirements  

### MLO  

We use [Warehouse Port](https://www.gta5-mods.com/maps/mlo-warehouse-port-add-on-sp-alt-v-ragemp-fivem-aspidemon) by aspidemon   

### Scripts  

[QTarget](https://github.com/overextended/qtarget) However [OXTarget](https://github.com/overextended/ox_target) ***should*** work, but is untested.  and will require you to change all instances of "qtarget" to "ox_target"  
[oxlib](https://github.com/overextended/ox_lib/)  
[oxmysql](https://github.com/overextended/oxmysql)  
[ESX](https://github.com/esx-framework/esx_core) This requires EX_Extended for stuff such as ESX.TriggerServerCallback  
[nh-keyboard](https://github.com/whooith/nh-keyboard) - For boss PC inputs, have included our build in the zip as i know this is one that can be funky with versions.  
[nh-keyboard our version](https://docs.dotroleplay.com/downloads/nh-keyboard.zip)

## Installation   

- Download the ZIP File from Keymaster.  
  It should be called MachsVendingVXXX With the XXX being a version number  
- Unzip The Zip File  
- Copy the "MachsVending" folder into your Resources folder  
- Run Vending.SQL - You may have to edit the items section for your server  
- Make sure you set "JobMenu" Key bind near the top of the Config File, as this will require client side changes if it needs to be changed  
- add "Start MachsVending" to your config, this needs to be started AFTER ESX,qtarget,oxlib, oxmsql, nh-keyboard. It Runs fine from a [category]  

## Known Issue

-When restarting the script often (such as testing when adding new machines/items) the Stock ped will sometimes show the menu for spawning a truck. A further restart fixes this. I have not had this happen naturally 
-Normal trickiness targeting stuff. This is a normal Targeting thing, just increase the distance variables in targeting.lua

---

## Job Description  

Chat GPT Generated a job description for this script  

"Are you ready to quench the thirst of the citizens of Los Santos? Join our team as a Vending Machine Operator! As a Vending Machine Operator, you will be responsible for restocking, maintaining and collecting money from vending machines located throughout the city. You will interact with a diverse range of customers, from thirsty construction workers to busy office executives, and provide them with a variety of refreshing drinks and snacks.  

Using our qtarget and ESX based system, you will be able to manage your inventory, restock machines, and collect payments. You will need to be quick on your feet, able to handle cash and interact with customers in a professional manner. Your success will depend on your ability to maintain and restock machines in a timely manner, keeping them in top condition and stocked with the latest products.  

If you're looking for a dynamic job with plenty of interaction and opportunities to work independently, then the Vending Machine Operator role is for you. Apply now and join our team today!"  

### TODO & Coming Soon  

- Add Cup Machines
- Add Police Notfiy
  
---

## Documentation  

### Config  

> There is quite a few text entries in the database, not documenting here as it should be easy enough to work out what they are for and they can mostly be treated as where you would change translations.  
> We Also use the database heavily in this, so for instance each vending machine has its own column for tracking each possible stock item. So adding items will require you to add columns in the database.  

#### ESX Shared Object  

```lua
ESX_OBJECT = 'esx:getSharedObject', --if you know what this is, you know if you need to change it
```

#### Debugging  

```lua
TargetDebug = false,  --This turns on debugging polys for objects that support it, must also be enable in targeting config.  
Debug = true, -- This is script debugging, only needs to be on when you need to debug  
```

#### Misc Script  

[Key bind docs](https://docs.fivem.net/docs/game-references/input-mapper-parameter-ids/keyboard/)  

```lua
CashLostPerVend = 3, --Treat this like a tax. With the default of 3, every $10 item sold gives the vending company $7
JobMenu = "f6", -- This must be changed before installing the script or it will require the player to set it manually CLIENT SIDE In the keybind settings
AlignMenu = "top-left", -- Where the ESX Job Menu will show 
```

#### Society And Jobs  

```lua
MVSociety = "society_vend", -- Society name, must match whats in the "addon_account" Table, you probably don't need to change this
SocietyJobName = "vend", -- Job Name, must match whats in "jobs" Table you probably don't need to change this
SocietyJobNameLabel = "Sharks Vending", -- Job Label. used for some UI/Popups, can be anything
Jobs = {["phi"] = 0, ["vend"] = 0}, --Jobs that can access the machines for stocking etc, ["jobname"] = rank -- Can be multi jobs
BossJob = {["phi"] = 2, ["vend"] = 2 }, -- Jobs that can access the boss actions
CashRequiredItem = "reaperskey" -- Item Required To Take Cash
```

#### Stock  

[FiveM Blips](https://docs.fivem.net/docs/game-references/blips/)  

```lua
AmmountPerVend = 1, -- How Much is given each time something is brought.
Currency = "$", --Whats shown for cash stuff IE "you have been given $10" when withdrwaing cash from machines 
StartStock = 22, --How much stock the machines should start with, keep in mind if the machine hasn't been used before, this is how much stock that will materialize in it
LowStock = 10, -- low stock value, at what point are the machines considered to have low stock. machines show on the map when "show low stock" in job menu is pressed
-- This is if ANY of the items in the machine have less than this value.
LowStockBlip = 752, -- Blips for machines with low stock (when menu option selected), 752 is alien ship
HQBlip = 752, -- Blip for the HQ Location
BlipColour = 2, -- Colour of HQ Blip
CompanyName = "Shark Vending", -- HQ Blip Title on map
```

#### Hot Drinks  

> This is a sample using the "hotdrinks" section of the config, similar name conventions are taken for other sections  

```lua
CoffeeTypeName = "coffee", --Best to leave this, is what also prepends in DB, this can be treated as the "machine type" or "machine name" not to be confused with models.
CoffeePrice = 20, -- Price of coffee per vend
TeaPrice = 20, -- Price of tea per vend
HotDrinksItemRefil = "hotdrinkpack", --Item Required to refill machine
HotDrinksRefillBy = 20, -- how much to refill machines by
HotDrinksRefilCost = 400,  --Cost of refills
HotDrinksItemList = {"coffee","tea"}, -- must match what is in MachsVending table in database, 
RemoveHotRefilAmmount = 1,  --How many refill items to take per refill (not sure why you would want this anything other than 1 but the option is there)
```

#### Props  

>This is where you add additional target-able props

```lua
----Prop Inits
----This is where you can add props for any custom vending machines
----https://gta-objects.xyz/
CoffeeVendingProps = {"prop_vend_coffe_01","p_ld_coffee_vend_s","p_ld_coffee_vend_01"}, -- These are the props for the Coffee vending machines
WaterVendingProps = {"prop_vend_water_01","prop_watercooler_dark","prop_watercooler"}, -- Water
SnackVendingProps = {"prop_vend_snak_01","prop_vend_snak_01_tu"}, -- Snakcs
ColdDrinkVendingProps = {"prop_vend_soda_01","prop_vend_soda_02"}, -- Cold Drinks
SlushPropList = {"prop_slush_dispenser","prop_juice_dispenser"}, -- Slush Machine and jucie
```

#### Warehouse and Stock  

```lua
BossPCLocation = vector3(-324.7753, -2775.9910, 6.2698), --A Box target for the boss pc
TruckSpawnPedModel = "s_m_m_dockwork_01", --The ped model to interact with for spawning truck
TruckSpawnPed = {V = vector3(-316.5530, -2768.5164, 4.9953), H = 345.4404}, -- Location for the ped to spawn, V Must be a vector3 and H Is heading
TruckSpawnLocation = {V = vector3(-329.2285, -2764.2124, 5.0004), H = 87.7528}, -- Location for the truck to spawn, V Must be a vector3 and H Is heading
t1ger_keys = true, -- True if you use t1ger keys, this will give you the keys to the vech
WarpIntoTruck = true, -- Should you warp the player into truck on spawn
UseCustomPlate = false,  -- Use custom plate text for all trucks spawned?
FallBackPlate = "Sharks", -- Also "customplate" - Set this if you don't use t1ger_dealerships but do use t1ger_keys or you want a custom plate

StockPedModel = "ig_chef2", -- the ped model for the stock ped
StockPed = {V = vector3(-323.1447, -2784.1116, 5.2070), H = 106.4621}, -- Where the ped should spawn 
StockText = "Take Stock ", -- Text shown when targeting

---Warehouse stock columns, these can be anything but MUST Match what is in the machsvendingwarehouse table
StockColdDrinks = "colddrinks", --this is the column name in the database that stores how many colddrink stock items there is 
StockHotDrinks = "hotdrinks", --this is the column name in the database that stores how many hotdrink stock items there is 
StockSnacks = "snacks", --this is the column name in the database that stores how many snack stock items there is 
StockWater = "water", --this is the column name in the database that stores how many water stock items there is 
StockDispenser = "dispenser", --this is the column name in the database that stores how many dispenser stock items there is 

StockDelivered = "Stock is now in the Warehouse ", --(item)
NotEnoughStock = "There is not enough stock",
TakeOutStockText = "You have taken ", -- Item, Ammmount 


TruckA_Model = "benson", --Truck 1 in the truck spawner, model namee
TruckA_Text = "Who Is Ben's Son?", -- Text for that
TruckB_Model = "pounder", -- Truck 2
TruckB_Text = "Pound Me?", -- More text
```

### Functions  

#### Client Functions  

##### GetStreetName

> Pass a set of coords to this, it will then break the coords into xyz
> it will then return the streetname, and cross street if there is one  

```lua
function GetStreetName(coords)
  local x,y,z = table.unpack(coords)
  local streetName, crossing = GetStreetNameAtCoord(x, y, z)
  streetName = GetStreetNameFromHashKey(streetName)
  ClientDebugPrint("Cross "..crossing)
  local message = ""
  if crossing ~= nil and crossing ~= 0 then
    crossing = GetStreetNameFromHashKey(crossing)
    message = streetName .. "_" .. crossing
  else
    message = streetName
  end
  return message
end
```

##### SendTextMessage(msg)

> This is where you can change notifications for the script, can be changed to whatever
> We use bulletin by default

```lua
function SendTextMessage(msg)
  exports.bulletin:SendWarning(msg, 5000)
end
```

##### BuildVendName(coords,type)

>The vending machine names are based of its type and its location, you probably dont need to change this unless your database doesn't like "_"

```lua
function BuildVendName(coords,type)
  local VendingName = type.."_"..coords.x.."_"..coords.y.."_"..coords.z
  return VendingName
end
```

##### ClientDebugPrint(msg)

>This is how we do client side debugging, if you need to do weird stuff with debug messages you can do it here

```
function ClientDebugPrint(msg)
  if Config.Debug == true then 
    print(msg)
  end
end
```

##### round(n) - Also in server side  

>Simple rounding function, pass a number to it and it will round it

```lua
function round(n)
  return n % 1 >= 0.5 and math.ceil(n) or math.floor(n)
end

```

#### Server Functions

##### PlayerHasItem(source,item)

>Checks if player has an item, change this if getInventoryItem(item) doesn't work for you

```lua
function PlayerHasItem(source,item)
local xPlayer = ESX.GetPlayerFromId(source)
local hasitem = xPlayer.getInventoryItem(item)
if hasitem.count > 0 then
  return true
else 
  return false
end
end
```

##### AddItem(source, item, ammount) & PlayerRemoveItem(source,item,ammount)

> Change these if removeInventoryItem(item, ammount) and addInventoryItem(item, ammount) don't work in your server 

```lua
function AddItem(source,item,ammount)
  local xPlayer = ESX.GetPlayerFromId(source)
  xPlayer.addInventoryItem(item, ammount)
end

function PlayerRemoveItem(source,item,ammount)
  local xPlayer = ESX.GetPlayerFromId(source)
  xPlayer.removeInventoryItem(item, ammount)
end
```

##### AddPlayerCash(source,cash), RemovePlayerCash(source,ammount) 

> Change these if addMoney(cash) or removeMoney(ammount) don't work for you 

```lua
function AddPlayerCash(source,cash)
  ServerDebugPrint("trying to add "..cash.." to "..source)
  local xPlayer = ESX.GetPlayerFromId(source)
  xPlayer.addMoney(cash)
end
function RemovePlayerCash(source,ammount)
  local xPlayer = ESX.GetPlayerFromId(source)
  xPlayer.removeMoney(ammount)
end

```

##### ServerDebugPrint(msg)

>This is how we do server side debugging, if you need to do weird stuff with debug messages you can do it here

```lua
function ServerDebugPrint(msg)
  if Config.Debug == true then 
    print(msg)
  end
end
```


### Adding new machine type  