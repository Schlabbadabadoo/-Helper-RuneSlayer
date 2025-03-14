# Rune-Slayer Function Usage on exploit level

## ⚡ Features

- Doesnt kick player when using it! further more user can actually make client do actions such as Block, Attack m1 & etc
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
