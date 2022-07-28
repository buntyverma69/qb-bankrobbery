# qb-bankrobbery



Step 1

Changed into qb-doorlock/config.lua

Replace with these line no 53 to 128


	{                                                          -- door pacific first door card b
		objName = 409280169,
		objCoords  = vec3(272.642151, 219.898712, 97.317978),
		textCoords = vec3(272.642151, 219.898712, 97.317978),
		authorizedJobs = { 'police' },
		objYaw = 340.00024414062,
		locked = true,
		pickable = false,
		distance = 1.5,
	},
	--door2 for pacific opened with thermite front near the card b door    [door id 2]
	{
		objName = 409280169,                                           
		objCoords  = vec3(270.103210, 212.922928, 97.317978),         
		textCoords = vec3(270.103210, 212.922928, 97.317978),
		authorizedJobs = { 'police' },
		objYaw = 340.00024414062,
		locked = true,
		pickable = false,
		distance = 1.5,
	},
	--door2 for pacific opened with thermite right near the vault door         [door id 3]
	{
		objName = 409280169,
		objCoords  = vec3(250.564209, 233.399384, 97.317978),       
		textCoords = vec3(250.564209, 233.399384, 97.317978),
		authorizedJobs = { 'police' },
		objYaw = 340.00024414062,
		locked = true,
		pickable = false,
		distance = 1.5
	},
	-- door3 for pacific opened with thermite after passing the door near vault
	{
		objName = 409280169,
		objCoords  = vec3(244.558014, 216.897278, 97.317978),
		textCoords = vec3(244.558014, 216.897278, 97.317978),
		authorizedJobs = { 'police' },
		objYaw = 340.00024414062,
		locked = true,
		pickable = false,
		distance = 1.5
	},
	-- Paleto Door 1 opened with security card A
	{
		objName = -2050208642,
		objCoords = vec3(-100.241867, 6464.549316, 31.884604),
		textCoords = vec3(-100.241867, 6464.549316, 31.884604),
		objYaw = 225.00010681152,
		authorizedJobs = { 'police' },
		locked = true,
		pickable = false,
		distance = 1.5
	},
 	-- Paleto Door 2 opened with thermite
	{
		objName = 'v_ilev_cbankvaulgate02',
		objCoords  = vec3(-106.26, 6476.01, 31.98),
		textCoords = vec3(-105.5, 6475.08, 31.99),
		objYaw = -45.0,
		authorizedJobs = { 'police' },
		locked = true,
		pickable = false,
		distance = 1.5
	},
	-- First Pacific Door opened with lockpick
	{
		objName = 643152522,
		objCoords  = vec3(225.646286, 228.886780, 97.323975),
		textCoords = vec3(225.646286, 228.886780, 97.323975),
		authorizedJobs = { 'police' },
		objYaw = 160.00025939941,
		locked = true,
		pickable = true,
		distance = 1.5
	},
	-- Second Pacific Door opened with lockpick
	{
		objName = 643152522,
		objCoords  = vec3(229.890533, 227.342010, 97.323975),
		textCoords = vec3(229.890533, 227.342010, 97.323975),
		authorizedJobs = { 'police' },
		objYaw = 340.00024414062,
		locked = true,
		pickable = true,
		distance = 1.5
	},


Step 2 (optional)
If want Replace Lockpick Minigame with cricle minigame
i am using sexy ps-ui here is snippets

Replace Into qb-doorlock/client/main.lua
Line no 486

RegisterNetEvent('lockpicks:UseLockpick', function(isAdvanced)

```lua

RegisterNetEvent('lockpicks:UseLockpick', function(isAdvanced)
	if not closestDoor.data or not next(closestDoor.data) or PlayerData.metadata['isdead'] or PlayerData.metadata['ishandcuffed'] or (not closestDoor.data.pickable and not closestDoor.data.lockpick) or not closestDoor.data.locked then return end
	exports['ps-ui']:Circle(function(success)
		if success then
			lockpickFinish(success)
			--print("success")
		else
			QBCore.Functions.Notify("Are you dumb? Go learn how to crack the door !", "success")
			--print("fail")
		end
	end, 4, 14) -- NumberOfCircles, MS
end)
```

Dependency 


https://github.com/ofcshiro/FlagUpdateFix   [ For Gabz Maps Not props showing in Vault Fix ]

https://github.com/buntyverma69/hacking   [ For Hacking Minigame ]



Credits:

https://github.com/Project-Sloth/ps-ui

https://github.com/qbcore-framework/qb-bankrobbery

https://github.com/qbcore-framework/qb-doorlock


https://github.com/ofcshiro/FlagUpdateFix 
