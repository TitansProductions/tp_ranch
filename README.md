# How can you create the best ranches.

## __Extra Custom Props / Objects:__

For having more props / objects for creating a ranch, i personally suggest the ones i use from SPOONI `Spooni_Stables_pack` and `Spooni_Stables2` which are the best custom props / objects to be used for creating ranches. 

## __Create new ranch areas:__

I personally suggest using the objectloader we provide you to the script for creating and spawning objects on the desired locations directly from the configuration file, those objects are local with a rendering system to properly load and unload when being nearby / not. You will no longer need any ymaps or xml files. 

*We already provide on the Object Loader folder the default ranch area and its objects / props - in case you dont see some props, it is because you are missing the SPOONI props that i have mentioned above.*

## How to clear the area around a ranch

To clear the area such as trees, bushes, grass, you can use: https://github.com/Spooni-Development/spooni_vegmod (SPOONI VEGMOD)

# How to implement a bucket system for the animals thirst consumption.

On `client/escrow_ignore.lua` file, we provide you (3) functions that you can implement the script of yours or another developer's for using the bucket properly.

*By default, we provide you TP Farming support in case you are having it.*

# How to edit existing animal's data

To edit / modify an animal is actually very difficult but once you learn it, it can be done very easily. 

The only possible way is by modifying through the tp_ranch database table where animals column is located. 

Keep in mind! The script or the server must be stopped, otherwise it will not load the new replaced data.

The easiest way is by `selecting` & `copying` animals database column (the data that it contains) and then, use **Visual Studio Code** to `paste` and edit manually on the desired animal the age, thirst, hunger, died (death state), product_duration or even sex (gender).

1. **age** - The age is in minutes, that means if you want your animal to be 5 years old, you have to calculate that in real days ( 5 * 24 * 60 ) which is **7200** (of course easiest is to search in google: 5 days in minutes)

2. **thirst & hunger** - 0 = min, 1000 = max

3. **died** - 0 = (alive), 1 = (dead)

4. **product_duration** - 0 = (cooldown reset for production), > 0 (bigger than 0, means cooldown is left in minutes to allow production - such as milking, shearing, etc).

5. **sex** - 0 = (male), 1 = (female)

Once you done editing the desired changes, copy the data and paste it on animals database table column (as mentioned above, the script or the server must be stopped).

In case you edited something and it is now corrupted and not loading the animals or receiving errors after your manual edit, i suggest removing animals data and inserting inside `[]` which clears and removes all your animals.


# Development Section & API Exports

## Exports

### Server Side

API Getter Function

```lua
local RanchAPI = exports.tp_ranch:getAPI()
```

1. Get all ranch data

```lua
--- @return table form.
local Ranches = RanchAPI.GetRanches()
```

2. Get all player owned ranch ids.

```lua
--- @return table form.
--- @param source - requires the online player source id.
local OwnedRanches = RanchAPI.GetPlayerOwnedRanchIds(source)
```

3. Get all player owned ranch data.

```lua
--- @return table form.
--- @param source - requires the online player source id.
local OwnedRanches = RanchAPI.GetPlayerOwnedRanchesData(source)
```

4. Set ranch ownership by player source.

```lua
--- @param ranchId - requires an existing ranch index name.
--- @param source - requires the online player source id.
RanchAPI.SetRanchOwnershipBySource(ranchId, source)
```

5. Set ranch ownership by player identifiers.

```lua
--- @param ranchId - requires an existing ranch index name.
--- @param identifier - requires a player steam hex.
--- @param charidentifier - requires a player character id.
RanchAPI.SetRanchOwnershipByIdentifiers(ranchId, identifier, charidentifier)
```

6. Remove ranch ownership by player identifiers.

```lua
--- @param ranchId - requires an existing ranch index name.
--- @param identifier - requires a player steam hex.
--- @param charidentifier - requires a player character id.
RanchAPI.RemovePlayerRanchOwnershipByIdentifiers(ranchId, identifier, charidentifier)
```

## Server Events

1. Add feeding capacity for cows and goats.

```lua

-- You don't need to add your own feeding capacity amount, it adds directly from `AddHungerCapacityOnHaybaleDeliver` config option where config_animals is.
--- @param ranchId - requires an existing ranch id.
--- @param amount - a non required parameter, it is used to add your own amount of capacity, if not used, it will use the mentioned option (max value is 1000 = 100% )
TriggerEvent("tp_ranch:server:shared:add_feeding_capacity", ranchId, amount) -- THIS IS A SERVER EVENT
```

2. Add water barrel capacity

```lua
-- You don't need to add your own add_barrel_capacity capacity amount, it adds directly from `Config.WaterSystem.AddBarrelCapacityOnBucketPouring` config option where config_animals is.
--- @param ranchId - requires an existing ranch id.
--- @param amount - a non required parameter, it is used to add your own amount of capacity, if not used, it will use the mentioned option (max value is 1000 = 100% )
TriggerEvent("tp_ranch:server:shared:add_barrel_capacity", ranchId, amount) -- THIS IS A SERVER EVENT
```

3. Add feeding capacity for chickens

```lua

-- You don't need to add your own feeding capacity amount, it adds directly from `AddProductCapacityCornOnDeliver` config option where config_animals is.
--- @param ranchId - requires an existing ranch id.
--- @param amount - a non required parameter, it is used to add your own amount of capacity, if not used, it will use the mentioned option (max value is 1000 = 100% )
TriggerEvent("tp_ranch:server:shared:add_chicken_feeding_capacity", ranchId, amount) -- THIS IS A SERVER EVENT
```

# Configuration Tutorials & Tips

The following explanation is related to a ranch creation - configuration since there are a lot of features and options. We will start from each configuration option which can be hard to understand what it requires.

1. **MilkContainerCoords** : This requires the coords to open the milk container storage on delivered milk jugs.

<img width="1160" height="862" alt="image" src="https://github.com/user-attachments/assets/e8cb68e1-ba32-46a8-af26-d984743d9b93" />

2. **WaterBarrelCoord** : This requires the coords to add water for the animals, otherwise those animals will die if they are left without any water available. When the barrel contains water, you don't have to do anything else, it just retrives the required values based on your animals and their thirst consumption. By default, we support **TP Farming** script for using the water barrel pouring system - you can use your own through `client/escrow_ignore.lua` file which also has **TP Farming** exports inside as examples.

<img width="1311" height="960" alt="image" src="https://github.com/user-attachments/assets/dddaa9fe-4945-4134-abb9-578ec4f20fb6" />
<img width="911" height="912" alt="image" src="https://github.com/user-attachments/assets/000b84de-1421-41d7-9e2c-b17c93640a1f" />
<img width="1019" height="860" alt="image" src="https://github.com/user-attachments/assets/fb655363-11a4-4d43-8c04-39b36c7a7fd5" />


3. **PitchForkObjectCoords** : This requires the object placement for picking up poop from cows or sheeps to make a fertilizer.

<img width="716" height="1130" alt="image" src="https://github.com/user-attachments/assets/29261fac-7444-4891-9f58-5391ca47ffe9" />
<img width="972" height="849" alt="image" src="https://github.com/user-attachments/assets/8a11d3cd-ac1b-49d7-9a4e-918f96543dde" />
<img width="1540" height="1119" alt="image" src="https://github.com/user-attachments/assets/3cf9afd2-0703-4e50-bc9e-133e75dfacd7" />
<img width="1338" height="980" alt="image" src="https://github.com/user-attachments/assets/c99c3be0-fc73-4951-9ad6-363371be84be" />
<img width="1205" height="709" alt="image" src="https://github.com/user-attachments/assets/0ce50e7a-b266-4654-956c-d0dcb13da352" />
<img width="926" height="727" alt="image" src="https://github.com/user-attachments/assets/fac5a723-e3f7-43b0-b72e-548fe8d4257b" />

4. **CauldronObject** : This requires the object placement to place the collected - picked up poop from the animals to create the fertilizer through a proccess.

<img width="1178" height="961" alt="image" src="https://github.com/user-attachments/assets/19de1cbb-700d-4904-a6fa-4538e6b2a81a" />

5. **DeliverProductCoords** This is for delivering the collected product (milk) jug from the cows into the milk container object (MilkContainerCoords).

<img width="2040" height="1310" alt="image" src="https://github.com/user-attachments/assets/1c8d0dd3-9ee6-4420-9533-dc1bcc1a8dd1" />

<img width="1482" height="972" alt="image" src="https://github.com/user-attachments/assets/a86004b6-53fc-4c1b-97b3-773df68b2b49" />
<img width="1215" height="796" alt="image" src="https://github.com/user-attachments/assets/b322ce83-921c-411d-88e0-9a9a66b9e4ec" />
<img width="1268" height="678" alt="image" src="https://github.com/user-attachments/assets/55679f60-c8c7-45e0-b127-abf859b33ffb" />
<img width="1022" height="602" alt="image" src="https://github.com/user-attachments/assets/cdc9d101-ba66-48fc-9f56-7b51966ae00f" />

7. **CowFoodCoords** This is for delivering the picked up haybale for feeding the cows. At first, you need to create nearby a hay pickup location from `Config.HayPickups`.

<img width="1477" height="1039" alt="image" src="https://github.com/user-attachments/assets/97b89abb-44c5-48ed-95d4-80e2494dbc1d" />
<img width="1165" height="840" alt="image" src="https://github.com/user-attachments/assets/919c3861-3e3d-4867-9664-f0db24f3c288" />
<img width="1441" height="1009" alt="image" src="https://github.com/user-attachments/assets/81a8e4f6-05a7-4856-9302-7bafeb42a53d" />

8. **FeedbagStandCoords** and **ChickenFoodCoords** This is related to the chicken(s), it is the feedbag hang object to pickup corn and feed the chickens. This also requires a delivery from `Config.CornPickups`.

<img width="1521" height="845" alt="image" src="https://github.com/user-attachments/assets/4ca70b55-8fff-4f22-aaf7-2cfec3e22e65" />
<img width="1144" height="961" alt="image" src="https://github.com/user-attachments/assets/3b3cedf1-caba-4767-8d82-309e8e537c72" />
<img width="1492" height="882" alt="image" src="https://github.com/user-attachments/assets/f1bf02e2-347f-42fb-9183-e7be47203c17" />
<img width="1143" height="962" alt="image" src="https://github.com/user-attachments/assets/889b45dd-4106-43a5-99a9-149e5c8533ea" />
<img width="970" height="496" alt="image" src="https://github.com/user-attachments/assets/5e7d750e-c188-4483-90f0-44330ae3e710" />
<img width="1001" height="723" alt="image" src="https://github.com/user-attachments/assets/efc7cfe9-bfb9-498d-9e76-27f6c151c4e5" />
<img width="1379" height="812" alt="image" src="https://github.com/user-attachments/assets/bc0991eb-0360-49b5-9225-097b49b0b975" />
