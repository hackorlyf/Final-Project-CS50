# Final-Project-CS50

# Friut Ninja

## Update-0 Importing Assets and Scene SetUp
1} Pulled 2 different Models and a Wood Texture for are Assets. One is the Whole friut and other is Sliced friut.

2} Turned off Compression for our Wood Texture as it was losing its quality because of it.

3} Added a Plane to our Scene and applied rotations and scaling to it such that it becomes the screen we'll be seeing with our wood texture on it.

4} Created a material named Background and added to it to our Mesh Renderer/Materials of Plane and then Dragged our Texture to Albedo and set smoothness to 0 while turning off our highlights and reflections because we don't need these on our Plane.

5} Also set Z of our plane to 5. This way we'll be veiwing a little above the origin, so we can now Spawn our fruits at the Origin.

![Standing with Gun](https://raw.githubusercontent.com/hackorlyf/portal-gun-RickandMorty/main/SS/Unity%202018.4.28f1%20Personal%20-%20PortalScene.unity%20-%20portal%20-%20PC%2C%20Mac%20%26%20Linux%20Standalone%20_DX11_%2026-08-2023%2002_09_20.png)
![] ()

## Update-1 Fruits Prefab
1} Created an Empty Game Object in our Hierarchy, named it as Fruit and dragged whole and slice model on it making them it's child.

2} Slice model is Turned off initially as we'll be turning it on when Player(Blade) collides with it causing a trigger.

3} We add Rigidbody component to our Fruit instance so that it becomes a Physics Object. Added a Sphere collider to it and set it to IsTrigger as we don't want fruits to interfere with each other while they are been launched up in the air.

4} Turned On our Slice Model to Add Rigidbody and colliders to it too. Here we need to add Box Colliders since they are halves and not a single whole sphere. Turned Off Drag and Kept Box Colliders as Non-Triggers Because Slices Colliding with each other creates an interesting dynamics.

5} Dragged our fruit object to Assets/Prefab creating a Prefab and renaming it as Fruit_Base. We created 5 Varients of Prefab named Fruit_Base naming them 5 different Fruits. Creating Varients helps us as changes(scripts) applied to our Fruit_Base will automatically be applied to all of its varient.

![] ()

## Update-2 Materials
1} Created 10 materials that is Inside and Outside for all of our 5 Fruits in our Assets/Materials. Dragged these materials to its respective Prefab in Mesh Renderer of Slice.

2} Set Colour of inside and outside of material according to the Fruit. Also set different sizes(Radius) so that Watermelon looks bigger than Kiwi and so on.

3} Set smoothness of inside material double to the outside material so that the inside looks more shiny, hence more juicy.

![] ()

## Update-3 Spawner
1} Create an empty Game Object in our Scene named Spawner. Create a C# script named Spawner which will be responsible for the logic behind Spawning our Fruits in the scene. Added this script as a component in our Game Object Spawner.

2} Added a Box Collider to our Spawner and set its Y to -15 as this box collider will be referenced for Spawning our fruits. All Fruits are Spawned on this Box collider hence this collider is kept as IsTriggered since we don't want Fruits actually colliding with it.

3} Created reference to our collider in our Spawner.cs script and intializing and getting this component in our Awake() function. Added OnEnable() and OnDisable() functions to start and stop all coroutines.

4} Created an array of Game Object for our Fruit prefab to store all the fruits we have created earlier stored in our Prefab folder. Added other variables such as minSpawnDelay, maxSpawnDelay, minAngle, maxAngle, minForce, maxForce, maxLifeTime doing what their name suggests.

5} Dragged fruit prefabs from Assets/Prefab to our Spawner.cs in Spawner Game Object. Added logic for Spawning fruits in our IEnumerator() function which yeilds return new Wait for seconds 2 when the function is first called so that the player gets ready and then while enabled it returns new Wait for seconds between minSpawnDelay & maxSpawnDelay.

![] ()

![] ()

![] ()

## Update-4 Blade
1} Added a Game Object named Blade to our Scene and added Playet tag to it.

2} Create a C# script named Blade which will be responsible for the logic behind Slicing our Fruits based on our mouse Input in the scene. Added this script as a component in our Game Object Blade.

![] ()

## Update-5 Blade Trail

![] ()

## Update-6 Slicing

![] ()

## Update-7 Particle Effect

![] ()

## Update-8 Scoring/UI

![] ()

## Update-9 Bombs

![] ()

## Update-10 Explode Sequence
