Ouroboros Unity3D CritterAI
=============

## Formerly CAINav
Ouroboros CritterAI modified

## Compilation (Unity): (Note: Unity3D-4.x, Unity3D-5.x-32bit, Unity3D-5.x-64bit already have compiled file, do not modify the source code, then without recompilation, directly you can)

	1: VS2013 / Jetbrains Rider and more open sources \ build \ unity \ cai-navigation-u3d.sln

	2: References settings on each subproject, add the Unity library reference:
		Unity \ Editor \ Data \ Managed \ UnityEditor.dll
		Unity \ Editor \ Data \ Managed \ UnityEngine.dll

	3: Compiling, and related files to copy critterai \ Unity3D-xx (refer to specific documents already compiled content Unity3D-5.x-64bit)

## Use Reference Project:

	1: The critterai \ \ Assets Unity copied to the corresponding item in Assets Unity3D-xx
	2: Open Unity3D to create a new project and add a 3D game terrain and sky boxes in the game scene, terrain create the resource name in a project called "New Terrain.asset"
	3: Copy all files and directories under the Unity3D / Assets directory to your Unity3D game corresponding to the item Assets, and now our Editor effect with the game asset library folder contents as shown below

![Cainav1] (https://raw.githubusercontent.com/RottenVisions/critterai/master/readme-src/cainav1.jpg)

	After initialization, the initialized 4:: select (Standard CritterAI-> Create NMGen Assets-> Navmesh Build) menu item in the game
	Project directory will appear in several files, they are as follows:
		CAIBakedNavmesh.asset
		MeshCompiler.asset
		NavmeshBuild.asset

	5: Adding a pathfinding instance can generate topographic grid Compiler, (CritterAI-> Create NMGen Assets-> Compiler: Terrain)

![Cainav2] (https://raw.githubusercontent.com/RottenVisions/critterai/master/readme-src/cainav2.jpg)

	We also need to set the terrain we created earlier to be bound to the TerrainCompiler.

![Cainav3] (https://raw.githubusercontent.com/RottenVisions/critterai/master/readme-src/cainav3.jpg)

	6: Start generating Navmesh

![Cainav4] (https://raw.githubusercontent.com/RottenVisions/critterai/master/readme-src/cainav4.jpg)

	7: Export to a file, then there will be two documents, "srv_" beginning of the file for server pathfinding. Can be used for another client to use the plug-in from locally.

![Cainav5] (https://raw.githubusercontent.com/RottenVisions/critterai/master/readme-src/cainav5.jpg)

	(Note: After the completion of generation projects proposed to delete Unity3D Assets \ paper on CAINav under Plugins, otherwise it will cause an error to start the game can not export the game for an unknown reason. This is probably due to the editor files contained in the binary - can try to fix this at a later time)

	8: Copy the "srv_" this file to the server asset inventory, for example: "D: \ ouro \ ouroboros \ src_assets \ res \ spaces \ idmo"
	After rebooting the server, the server will load the scene for this pathfinding resource (Note: To find the right way, server entity must be in the valid range of coordinates that must be on the ground Navmesh)

	(For more information please refer to the plugin's official website: http: //www.critterai.org/projects/cainav/)


## Demonstration

	None yet
