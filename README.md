```lua
-- // Loadstring
if game.CoreGui:FindFirstChild("Aux_Pineapple") then
    game.CoreGui.Aux_Pineapple:Destroy()
end





local owner = "MirayXS"
local branch = "anti-steal"

local function webImport(file)
    return loadstring(game:HttpGetAsync(("https://raw.githubusercontent.com/%s/Aux/%s/%s.lua"):format(owner, branch, file)), file .. '.lua')()
end

webImport("Pineapple")
```
