
# Q & A:

## How to create a ranch:

1. Creating a ranch is through `config/config_ranches.lua` configuration file and not through a command or an in-game menu. By that, you can easily modify a ranch anytime.

## How to implement a bucket system for feeding the cows.

On `client/escrow_ignore.lua` file, we provide you (3) functions that you can implement the script of yours or another developer's for using the bucket properly.

*By default, we provide you TP Farming support in case you are having it.*

## How to clear the area around the ranch or add new furnitures - objects.

1. To clear the area such as trees, bushes, grass, you can use: https://github.com/Spooni-Development/spooni_vegmod (SPOONI VEGMOD)
2. To add furnitures - objects you can use a script that i provide for free: https://github.com/TitansProductions/tp_objectloader

# Configuration Tutorials & Tips

The following explanation is related to a ranch creation - configuration since there are a lot of features and options. We will start from each configuration option which can be hard to understand what it requires.

1. **MilkContainerCoords** : This requires the coords to open the milk container storage on delivered milk jugs.

<img width="1160" height="862" alt="image" src="https://github.com/user-attachments/assets/e8cb68e1-ba32-46a8-af26-d984743d9b93" />

2. **WaterBarrelCoord** : This requires the coords to add water for the animals, otherwise those animals will die if they are left without any water available. When the barrel contains water, you don't have to do anything else, it just retrives the required values based on your animals and their thirst consumption.

<img width="1311" height="960" alt="image" src="https://github.com/user-attachments/assets/dddaa9fe-4945-4134-abb9-578ec4f20fb6" />

3. **PitchForkObjectCoords** : This requires the object placement for picking up poop from cows or sheeps to make a fertilizer.

<img width="716" height="1130" alt="image" src="https://github.com/user-attachments/assets/29261fac-7444-4891-9f58-5391ca47ffe9" />

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

8. **FeedbagStandCoords** This is related to the chicken(s), it is the feedbag hang object to pickup corn and feed the chickens. This also requires a delivery from `Config.CornPickups`.

<img width="1521" height="845" alt="image" src="https://github.com/user-attachments/assets/4ca70b55-8fff-4f22-aaf7-2cfec3e22e65" />
<img width="1144" height="961" alt="image" src="https://github.com/user-attachments/assets/3b3cedf1-caba-4767-8d82-309e8e537c72" />
