# Rune-Slayer Function Usage on exploit level

## ⚡ Features

### General Utilities
- **`Rune.LoopStart(name, func, interval)`**: Starts a loop that executes a function at a specified interval.
- **`Rune.LoopStop(name)`**: Stops a running loop.
- **`Rune.GetCharacterComponents()`**: Retrieves essential components of the player's character.
- **`Rune.GetPlayerGui()`**: Returns the player's GUI instance.

### Movement
- **`Rune.PathfindTo(targetPosition)`**: Moves the player to a target position using pathfinding.
- **`Rune.TweenTo(speed, ...)`**: Moves the player to a target position using `TweenService`.
- **`Rune.CustomTweenTo(maxSpeed, targetCFrame)`**: Moves the player manually, ensuring the speed does not exceed a maximum.

### Interaction
- **`Rune.Interact(Object, Action)`**: Interacts with a specified object using a given action.
- **`Rune.NearestInteract()`**: Finds and interacts with the nearest interactable object.

### Combat
- **`Rune.Parry()`**: Executes a parry action.
- **`Rune.getNearestMob(maxDistance)`**: Finds the nearest mob within a specified distance.

### Harvesting
- **`Rune.IsValidHarvest(Item)`**: Checks if an item is valid for harvesting.
- **`Rune.LookUpinHarvest(ItemName, radius, originPosition)`**: Finds the nearest harvestable item by name.
- **`Rune.LookUpinMob(MobName, radius, originPosition)`**: Finds the nearest mob by name.

### Inventory Management
- **`Rune.RefreshInventory()`**: Refreshes the inventory cache.
- **`Rune.WatchInventory()`**: Watches for changes in the inventory and updates the cache.
- **`Rune.LookUpInventory(searchTerm, partialMatch)`**: Searches the inventory for items matching a term.
- **`Rune.SellItem(itemName)`**: Sells a specific item from the inventory.

### Miscellaneous
- **`Rune.ServerHop()`**: Hops to a new server with fewer players.
- **`Rune.PlaySound(id)`**: Plays a sound at the player's position.
- **`Rune.MobNotifier(lf, ifnot)`**: Notifies the player when specific mobs spawn.
- **`Rune.MobChecker(check)`**: Checks if specific mobs exist in the game.
<br/>
# 🔌 Installation

```lua
local Rune = loadstring(game:HttpGet("https://raw.githubusercontent.com/Schlabbadabadoo/-Helper-RuneSlayer/refs/heads/main/RuneLibrary"))()
```
<br/>

# 📜 Usage
```lua
local Map = workspace:WaitForChild("Map")
local Rune = loadstring(game:HttpGet("https://raw.githubusercontent.com/Schlabbadabadoo/-Helper-RuneSlayer/refs/heads/main/RuneLibrary"))()
Rune.SellEvent(true)
task.delay(1,function()
    Rune.SellEvent(false)
end)
Rune.SellItem("Flax Hat")
Rune.WatchInventory()
Rune.RefreshInventory()
Rune.LoopStart("AutoSellOres", function()
    Rune.LookUpInventory("Ore", true) 
    if #Rune.FoundItems > 0 then
        for _, ore in ipairs(Rune.FoundItems) do 
            print("Selling:", ore.Name)
            Rune.SellItem(ore.Name)
            task.wait(1)
        end
    else
        print("No ores found!")
    end
end, 0.1)
task.delay(5,function()
Rune.LoopStop("AutoSellOres")
end)
Rune.NearestInteract()
Rune.Interact(Map:WaitForChild("Furnace"), "Craft") 
Rune.Smelt(1,"Iron Ore","Iron Bar")
Rune.MasterSignal("WeaponArtHold")
Rune.MouseInput("Button1Down")
task.delay(1, function()
	Rune.MouseEvent("Button1Up")
	Rune.MasterSignal("WeaponArt")
	warn("Stopped")
end)
```
<br/>

## Credits

- awakenkn / https://e-z.bio/awaken
