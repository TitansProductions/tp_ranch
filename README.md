
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


`MilkContainerCoords` : This requires the coords to open the milk container storage on delivered milk jugs.
<img width="1160" height="862" alt="image" src="https://github.com/user-attachments/assets/e8cb68e1-ba32-46a8-af26-d984743d9b93" />

`WaterBarrelCoords` : This requires the coords to add water for the animals, otherwise those animals will die if they are left without any water available. When the barrel contains water, you don't have to do anything else, it just retrives the required values based on your animals and their thirst consumption.

<img width="1311" height="960" alt="image" src="https://github.com/user-attachments/assets/dddaa9fe-4945-4134-abb9-578ec4f20fb6" />

`PitchForkObjectCoords` : This requires the object placement for picking up poop from cows or sheeps to make a fertilizer.

<img width="716" height="1130" alt="image" src="https://github.com/user-attachments/assets/29261fac-7444-4891-9f58-5391ca47ffe9" />
