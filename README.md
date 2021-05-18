```lua
repeat
    wait()
until game:IsLoaded()
wait()
print(string.rep("\n", 50))

if not syn or not syn.request then
    getgenv().syn = {}
    syn.request = http_request or request or (http and http.request)
end

local http_request = http_request or request or (http and http.request) or (syn and syn.request)

if KRNL_LOADED then
    getgenv().syn = nil
end
local exploit_type
if PROTOSMASHER_LOADED then
    exploit_type = "ProtoSmasher"
    print("ProtoSmasher")
elseif is_sirhurt_closure then
    exploit_type = "Sirhurt"
    print("Sirhurt")
elseif SENTINEL_LOADED then
    exploit_type = "Sentinel"
    print("Sentinel")
elseif syn then
    exploit_type = "Synapse X"
    wait(10)
    writefile("PineAppleSyn.txt", syn.request({Url = "https://github.com/MirayXS/Aux/raw/syn/UI.rbxm"}).Body)
    function wrap(script)
        f, e = loadstring(script.Source)
        print(f, e)
        env = setmetatable({},{__index = function(self, key) if key == "script" then return script end return getfenv()[key] end})
        setfenv(f, env)
        return f
    end
    e = game:GetObjects(getsynasset("PineAppleSyn.txt"))[1]
    e.Parent = game.CoreGui
    for i, v in pairs(e:GetDescendants()) do
        if v.ClassName:match("Script") then
            spawn(wrap(v))
        end
    end
elseif KRNL_LOADED then
    exploit_type = "KRNL"
    print("KRNL")
elseif hookfunction_raw and hmjdfk then
    exploit_type = "Fluxus Mac Free"
    print("Fluxus Mac Free")
    if not getconnections then
        getgenv().getconnections = function()
            return {}
        end
        getgenv().set_thread_context = function()
            return
        end
        getgenv().fluxus_loaded = true
    end
elseif FLUXUS_LOADED then
    exploit_type = "Fluxus"
    print("Fluxus")
elseif getexecutorname then
    exploit_type = "Script-Ware"
    print("Script-Ware")
    -- else
    -- game.Players.LocalPlayer:Kick("Your executor is not supported!")
    -- error("Executor not Supported!")
    -- end
end
if true then
    writefile("PineApple.txt", 'exploit_type = "' .. exploit_type .. '"')
    print(string.rep("=", 50))
    print("[Aux | Pineapple]: Authenticated!")
    print(string.rep("=", 50))
    print('[Aux | pineapple]: exploit_type = "' .. exploit_type .. '"')
    print(string.rep("=", 50))
end

wait(5)

--// Aux | Pineapple - Cracked Loader
--// Version 1.1 (alpha)
repeat wait() until game:IsLoaded()
repeat wait() until game.Players.LocalPlayer
local crack = 1
local cracked = 1
for i = crack, cracked do
loadstring("\108\111\99\97\108\32\111\119\110\101\114\32\61\32\34\77\105\114\97\121\88\83\34\10\108\111\99\97\108\32\98\114\97\110\99\104\32\61\32\34\108\111\97\100\101\114\34\10\10\108\111\99\97\108\32\102\117\110\99\116\105\111\110\32\119\101\98\73\109\112\111\114\116\40\102\105\108\101\41\10\32\32\32\32\114\101\116\117\114\110\32\108\111\97\100\115\116\114\105\110\103\40\103\97\109\101\58\72\116\116\112\71\101\116\65\115\121\110\99\40\40\34\104\116\116\112\115\58\47\47\114\97\119\46\103\105\116\104\117\98\117\115\101\114\99\111\110\116\101\110\116\46\99\111\109\47\37\115\47\65\117\120\47\37\115\47\37\115\46\108\117\97\34\41\58\102\111\114\109\97\116\40\111\119\110\101\114\44\32\98\114\97\110\99\104\44\32\102\105\108\101\41\41\44\32\102\105\108\101\32\46\46\32\39\46\108\117\97\39\41\40\41\10\101\110\100\10\10\119\101\98\73\109\112\111\114\116\40\34\118\49\46\49\95\97\108\112\104\97\34\41\10")()
end

wait(5)

-- // Loadstring
if game.CoreGui:FindFirstChild("Aux_Pineapple") then
    game.CoreGui.Aux_Pineapple:Destroy()
end



-- // Old: loadstring(game:HttpGet(("https://raw.githubusercontent.com/MirayXS/Aux/main/Pineapple.lua"), true))()



local owner = "MirayXS"
local branch = "main"

local function webImport(file)
    return loadstring(game:HttpGetAsync(("https://raw.githubusercontent.com/%s/Aux/%s/%s.lua"):format(owner, branch, file)), file .. '.lua')()
end

webImport("Pineapple")
```
