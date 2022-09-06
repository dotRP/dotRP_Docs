# Core_Crafting

This is how you add items to core_crafting!  

#FOR ESX

## Adding Items to the Database.  

First you need to add all the items you want to use to the Database, a good way of doing this is in a CSV File!
[ITEMS.CSV](docs/items.csv)
| name                                                            | label                                        | weight                               | rare     | can\_remove | degrade\_modifier | unique   | description      | x                   | y | category                |
| --------------------------------------------------------------- | -------------------------------------------- | ------------------------------------ | -------- | ----------- | ----------------- | -------- | ---------------- | ------------------- | - | ----------------------- |
| The name of the item, always lowercase, no spaces or spec chars | How you want it to be displayed in inventory | a weight (0 if using core inventory) | Always 0 | Always 1    | Best set to 1     | Always 0 | opt discription  | Core inventroy Size |   | Core inventory category |
| drink\_flaming\_slater                                          | Flaming Slater                               | 0                                    | 0        | 1           | 1                 | 0        | Boom Peepo Drunk | 1                   | 1 | drinks                  |

> For images the must match the name and be placed it the inventory's picture location. The same images will need to be put in the \core_crafting\html\img folder.

## Making items useable  


>This is for stuff that you want to be consumable, like rum and coke, but you wouldn't add ice here.  
If you want the person to be able to drink/eat it it needs to be here  
This would go in your food script. We used to use [viv_snackies](https://github.com/Vivi4n/viv_snackies) but have since moved to our own functions script.  
This could also be added to esx_basicneeds


> For non alcoholic drinks 
```
ESX.RegisterUsableItem('cola', function(source)  // Cola is name of item in DB
    local xPlayer = ESX.GetPlayerFromId(source)
    xPlayer.removeInventoryItem('cola', 1) // Cola is name of item in DB
    TriggerClientEvent('esx_status:add', source, 'thirst', 220000) //How much to fill up thirst - 200k is a decent number
    TriggerClientEvent('esx_basicneeds:onDrink', source)
    TriggerClientEvent('esx:showNotification', source, _U('used_cola')) //used_cola (for translations)  
end)  
```
> For alcoholic drinks  
```
ESX.RegisterUsableItem('whiskey', function(source) //Whiskey is db item name
    local xPlayer = ESX.GetPlayerFromId(source)
    xPlayer.removeInventoryItem('whiskey', 1) //Whiskey is db item name
    TriggerClientEvent('esx_status:add', source, 'drunk', 220000) //How shitfaced you want people to be - 200k is a decent number
    TriggerClientEvent('esx_status:add', source, 'thirst', 220000) //How much to fill up thirst - 200k is a decent number
    TriggerClientEvent('esx_optionalneeds:onDrink', source)
    TriggerClientEvent('esx:showNotification', source, _U('used_whiskey')) //used_whiskey (for translations)
end)  
```
> For Food  
```
ESX.RegisterUsableItem('fishbait', function(source) //fishbait is item name in db
    local xPlayer = ESX.GetPlayerFromId(source)
    xPlayer.removeInventoryItem('fishbait', 1) //fishbait is item name in db
    TriggerClientEvent('esx_status:add', source, 'hunger', 8000) //how much to fill up food (8k is low)
    TriggerClientEvent('esx_basicneeds:onEat', source)
    TriggerClientEvent('esx:showNotification', source, _U('used_fishbait')) //used_fishbait (for translations)
end)
```

> Then into the locales file add the correct locales  

['used_fishbait'] ='You ate my wet meat',  // What comes up when you use the item

## Adding to Core_Crafting
