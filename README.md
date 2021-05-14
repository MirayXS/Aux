```lua
repeat wait() until game:IsLoaded() wait() print(string.rep("\n", 50))

if not syn or not syn.request then
    getgenv().syn = {}
    syn.request = http_request or request or (http and http.request)
end

local http_request = http_request or request or (http and http.request) or (syn and syn.request)

if KRNL_LOADED then getgenv().syn = nil end 
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
        getgenv().set_thread_context = function() return end
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
    writefile("PineApple.txt", "exploit_type = \""..exploit_type.."\"")
    print(string.rep("=", 50))
    print("[Aux | Pineapple]: Authenticated!")
    print(string.rep("=", 50))
    print("[Aux | pineapple]: exploit_type = \""..exploit_type.."\"")
    print(string.rep("=", 50))
end

wait(5)










-- // Loadstring
if game.CoreGui:FindFirstChild("Aux_Pineapple") then
    game.CoreGui.Aux_Pineapple:Destroy()
end

loadstring(game:HttpGet(("https://raw.githubusercontent.com/MirayXS/Aux/main/Pineapple.lua"),true))()
```
