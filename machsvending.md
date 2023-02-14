---
id: MachsVedning
---

# MachsVending 

## UNDER CONSTRUCTION    

Please read our [Documentation](https://docs.dotroleplay.com/MachsVending) For help with configuration  

---
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


## Requirements  

### MLO  

We use [Warehouse Port](https://www.gta5-mods.com/maps/mlo-warehouse-port-add-on-sp-alt-v-ragemp-fivem-aspidemon) by aspidemon   

### Scripts  

[QTarget](https://github.com/overextended/qtarget) However [OXTarget](https://github.com/overextended/ox_target) ***should*** work, but is untested.  and will require you to change all instances of "qtarget" to "ox_target"  
[oxlib](https://github.com/overextended/ox_lib/)  
[oxmysql](https://github.com/overextended/oxmysql)  
[ESX](https://github.com/esx-framework/esx_core) This requires EX_Extended for stuff such as ESX.TriggerServerCallback  

## Installation   










## Job Description 

Chat GPT Generated a job description for this script  


"Are you ready to quench the thirst of the citizens of Los Santos? Join our team as a Vending Machine Operator! As a Vending Machine Operator, you will be responsible for restocking, maintaining and collecting money from vending machines located throughout the city. You will interact with a diverse range of customers, from thirsty construction workers to busy office executives, and provide them with a variety of refreshing drinks and snacks.  

Using our qtarget and ESX based system, you will be able to manage your inventory, restock machines, and collect payments. You will need to be quick on your feet, able to handle cash and interact with customers in a professional manner. Your success will depend on your ability to maintain and restock machines in a timely manner, keeping them in top condition and stocked with the latest products.  

If you're looking for a dynamic job with plenty of interaction and opportunities to work independently, then the Vending Machine Operator role is for you. Apply now and join our team today!"  




### TODO
- Add Slush machines / Cup Machines
- Disposable Cups 
- add cash to society 
- order stock 
- del vech
- Boss Menu / Society  
- Warehouse to get stock from  

