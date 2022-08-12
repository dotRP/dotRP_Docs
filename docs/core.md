# Core_Inventory / Core_Clothing

> The stuff we have learnt trying to get these working. 

#FOR ESX
>Note; You might not Need core_weapons if you have Core_Inventory

Thanks to all the CORE staff & discord members (esp Grnphnx for the bits of code i have found to build this) 

>As per CORE documentaions do the following


>ADD/REPLACE THESE FUNCTIONS IN es_extended/server/classes/player.lua

  	function self.getInventory(minimal, inventory)
			 inventory = inventory or 'content-' ..  self.identifier:gsub(":", "")

        	return exports['core_inventory']:getInventory(inventory)
	end

	function self.getInventoryItem(name, inventory)
		 inventory = inventory or 'content-' ..  self.identifier:gsub(":", "")

        return exports['core_inventory']:getItem(inventory, name)
	end

	function self.addInventoryItem(name, count, metadata, inventory)
		 inventory = inventory or 'content-' ..  self.identifier:gsub(":", "")

        return exports['core_inventory']:addItem(inventory, name, count, metadata)
	end

	function self.removeInventoryItem(name, count, inventory)
		 inventory = inventory or 'content-' ..  self.identifier:gsub(":", "")

        return exports['core_inventory']:removeItem(inventory, name, count)
	end

	function self.canCarryItem(name, count, inventory)
		 inventory = inventory or 'content-' ..  self.identifier:gsub(":", "")

        return exports['core_inventory']:canCarry(inventory, name, count)
	end
	
>1) Import SQL File  
 2) Add an x,y Vaule to all items (this sets how much space it takes up in the inventory)  
 3) Give all Weapons the "weapons" catagory  
 4) Set all weapon names to lowercase (This changes the command from /giveweapon to /giveitem  
 
 ---
 
 # Weapon Purchasing  
 >1) REPLACE xplayer.addWeapon(GUNNAME,0) in weapons shops to xplayer.addInventoryItem(GUNNAME, 1) - This may be need to be done in scripts like esx_police  
  2) Add the SQL File [Core Gun Parts SQL](docs/coregunparts.md) to your database (This adds attachments to the database to use as items)  
  3)
  
 # Pause Menu
 
 >if your pause menu is not working, remove this line in client.lua (around 316 for me)  
DisableControlAction(0, 199, true)