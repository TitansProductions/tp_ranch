# How can you create the best ranches.

## __Custom Props / Objects:__

We personally use SPOONI `Spooni_Stables_pack` and `Spooni_Stables2` which are the best custom streamed objects to be used for creating ranches. As mentioned above, if you already have those or you buy them from SPOONI, you can use https://github.com/TitansProductions/tp_objectloader which is our objectloader for placing objects to the desired positions without streaming but only through a configuration file.

## __Create new ranch areas:__

I personally suggest using our free script which is [**TP Object Loader**](https://github.com/TitansProductions/tp_objectloader) is used to create and spawn objects on the desired locations directly from the configuration file, those objects are client - side with a rendering system to properly load and unload when being nearby / not. You will no longer need any ymaps or xml files. 

## How to clear the area around a ranch

To clear the area such as trees, bushes, grass, you can use: https://github.com/Spooni-Development/spooni_vegmod (SPOONI VEGMOD)

# How to implement a bucket system for the animals thirst consumption.

On `client/escrow_ignore.lua` file, we provide you (3) functions that you can implement the script of yours or another developer's for using the bucket properly.

*By default, we provide you TP Farming support in case you are having it.*

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
