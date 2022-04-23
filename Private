if game.PlaceId == 6284583030 then
    local start = tick()
    repeat task.wait() until game:isLoaded()
    repeat task.wait() until game:GetService("Players")
    repeat task.wait() until game:GetService("Players").LocalPlayer
    repeat task.wait() until game:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
    repeat task.wait() until game:GetService("Players").LocalPlayer.PlayerGui.Main.Enabled
    repeat task.wait() until game:GetService("Workspace"):FindFirstChild('__MAP')
end

local Mercury = loadstring(game:HttpGet("https://raw.githubusercontent.com/Jaaaaay2/Lib/main/Mercury%20Lib/sectionsource.lua"))()

local VirtualUser = game:GetService('VirtualUser')
local HttpService = game:GetService("HttpService")
local RunService = game:GetService("RunService")

local GUI = Mercury:Create{
    Name = "Pet Simulator X",
    Size = UDim2.fromOffset(600, 400),
    Theme = Mercury.Themes.Dark,
    Link = "http://discord.gg/mYxX2e5cRR"
}

local GC = getconnections or get_signal_cons
if GC then
    for i,v in pairs(GC(game.Players.LocalPlayer.Idled)) do
        if v["Disable"] then
            v["Disable"](v)
        elseif v["Disconnect"] then
            v["Disconnect"](v)
        end
    end
else
    print("Unlucky.")
    local vu = game:GetService("VirtualUser")
    game:GetService("Players").LocalPlayer.Idled:connect(function()
        vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
        wait(1)
        vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
    end)
end

spawn(function()
    while task.wait() do
        GUI:Set_Status("Made by Levia")
        wait(5)
        GUI:Set_Status("http://discord.gg/mYxX2e5cRR")
        wait(5)
    end
end)

local Tab = GUI:Tab{
	Name = "Farm",
	Icon = "rbxassetid://9208984209"
}

local SectionSettings = Tab:Section{
    Name = "Settings"
}

SectionSettings:Toggle{
    Name = "Auto Collect Bags", 
    StartingState = false, 
    Callback = function(autolootfunc)
    _G.AutoLootbags = autolootfunc
end
}

spawn(function()
    local Running = {}
    while task.wait() do
        if _G.AutoLootbags then
            for i, v in pairs(game:GetService("Workspace")["__THINGS"].Lootbags:GetChildren()) do
                pcall(function()
                    if v ~= nil and v.ClassName == 'MeshPart' then
                        if not Running[v.Name] then
                            Running[v.Name] = true
                            local StartTick = tick()
                            v.Material = "SmoothPlastic"
                            v.Transparency = 1
                            v.Reflectance = 0
                            for i2,v2 in pairs(v:GetChildren()) do
                                if not string.find(v2.Name, "Body") then
                                    v2:Destroy()
                                end
                            end
                            repeat task.wait()
                                v.CFrame = game.Players.LocalPlayer.Character:WaitForChild("HumanoidRootPart").CFrame
                                local args = {
                                    [1] = {
                                        [1] = v.Name,
                                        [2] = Vector3.new(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.X, game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Y, game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Z)
                                    }
                                }
                    
                                workspace.__THINGS.__REMOTES:FindFirstChild("collect lootbag"):FireServer(unpack(args))
                            until v == nil or not v.Parent or tick() > StartTick + 1 or _G.AutoLootbags == false
                            Running[v.Name] = nil
                        end
                    end
                end)
            end
        end
    end
end)

--// Services \\--
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "join coin")
workspace.__THINGS.__REMOTES.MAIN:FireServer("a", "farm coin")
workspace.__THINGS.__REMOTES.MAIN:FireServer("a", "claim orbs")
workspace.__THINGS.__REMOTES.MAIN:FireServer("a", "change pet target")
workspace.__THINGS.__REMOTES.MAIN:FireServer("a", "toggle setting")

local CurrencyOrder = {"Rainbow Coins", "Tech Coins", "Fantasy Coins", "Coins", "Diamonds",}

local IMightKillMyselfCauseOfThis = {
    --Misc
    ['VIP'] = {'VIP'; 'VIP FRONT'};
    --Spawn
    ['Town'] = {'Town', 'Town FRONT'};
    ['Forest'] = {'Forest', 'Forest FRONT'};
    ['Beach'] = {'Beach', 'Beach FRONT'};
    ['Mine'] = {'Mine', 'Mine FRONT'};
    ['Winter'] = {'Winter', 'Winter FRONT'};
    ['Glacier'] = {'Glacier', 'Glacier Lake'};
    ['Desert'] = {'Desert', 'Desert FRONT'};
    ['Volcano'] = {'Volcano', 'Volcano FRONT'};
    -- Fantasy init
    ['Enchanted Forest'] = {'Enchanted Forest', 'Enchanted Forest FRONT'};
    ['Ancient Island'] = {'Ancient Island'; 'Heaven Island FRONT'};
    ['Samurai Island'] = {'Samurai Island', 'Samurai Island FRONT'};
    ['Candy Island'] = {'Candy Island'; 'Candy Island FRONT'};
    ['Haunted Island'] = {'Haunted Island', 'Haunted Island FRONT'};
    ['Hell Island'] = {'Hell Island'; 'Hell Island FRONT'};
    ['Heaven Island'] = {'Heaven Island'; 'Heaven Island FRONT'};
    -- Tech
    ['Tech City'] = {'Tech City'; 'Tech City FRONT'};
    ['Dark Tech'] = {'Dark Tech'; 'Dark Tech FRONT'};
    ['Steampunk'] = {'Steampunk'; 'Steampunk FRONT'};
    ['Alien Forest'] = {"Alien Forest"; "Alien Forest FRONT"};
    ['Alien Lab'] = {"Alien lab"; "Alien Lab FRONT"};
    ['Glitch'] = {"Glitch"; "Glitch FRONT"};
    ['Hacker Portal'] = {"Hacker Portal"; "Hacker Portal FRONT"};
    -- Axolotls
    ['Axolotl Ocean'] = {"Axolotl Ocean"; "Axolotl Ocean FRONT"};
    ['Axolotl Deep Ocean'] = {"Axolotl Deep Ocean"; "Axolotl Deep Ocean FRONT"};
    ['Axolotl Cave'] = {"Axolotl Cave"; "Axolotl Cave FRONT"};
    -- PIXEL
    ['Pixel Forest'] = {'Pixel Forest'; 'Pixel Forest FRONT'};
    ['Pixel Kyoto'] = {'Pixel Kyoto'; 'Pixel Kyoto FRONT'};
    ['Pixel Alps'] = {'Pixel Alps'; 'Pixel Alps FRONT'};
}

local AreaList = {
    'All'; 'VIP';
    '-- SPAWN WORLD --';
    'Town'; 'Forest'; 'Beach'; 'Mine'; 'Winter'; 'Glacier'; 'Desert'; 'Volcano';
    '-- FANTASY WORLD --';
    'Enchanted Forest'; 'Ancient Island'; 'Samurai Island'; 'Candy Island'; 'Haunted Island'; 'Hell Island'; 'Heaven Island';
    '-- TECH WORLD --';
    'Tech City'; 'Dark Tech'; 'Steampunk'; 'Alien Lab'; 'Alien Forest'; 'Glitch'; 'Hacker Portal';
    '-- AXOLOTLS WORLD --';
    'Axolotl Ocean'; 'Axolotl Deep Ocean'; 'Axolotl Cave';
    '-- PIXEL WORLD --';
    'Pixel Forest'; 'Pixel Kyoto'; 'Pixel Alps';
}

local Chests = {
    "All";
    '-- SPAWN WORLD --';
    "Volcano Magma Chest";
    '-- FANTASY WORLD --';
    "Enchanted Forest Chest"; "Ancient Island Enchanted Chest"; "Haunted Island Haunted Chest"; "Hell Island Hell Chest"; "Heaven Island Angel Chest"; "Heavens Gate Grand Heaven Chest";
    '-- TECH WORLD --',
    "Giant Tech Chest"; "Giant Steampunk Chest"; "Giant Alien Chest";
    '-- AXOLOTLS WORLD --';
    "Giant Ocean Chest";
    '-- PIXEL WORLD --';
    "Giant Pixel Chest";
}


local CratesMasteryList = {"Town Crate"; "Forest Crate"; "Beach Crate"; "Mine Crate"; "Desert Crate"; "Volcano Crate"; "Winter Crate"; "Glacier Crate"; "Enchanted Forest Crate"; "Ancient Island Crate"; "Samurai Island Crate"; "Candy Island Crate"; "Haunted Island Crate"; "Hell Island Crate"; "Heaven Island Crate"; "Tech City Crate"; "Dark Tech Crate"; "Alien Forest Crate"; "Axolotl Ocean Crate"; "Pixel Forest Crate"; "Pixel Alps Crate";}

local CoinsPilesMasteryList ={"Town Coins", "Town Large Coins", 'Town Tiny Coins', "Forest Coins", "Forest Large Coins", "Forest Tiny Coins", "Beach Coins", "Beach Large Coins", "Beach Tiny Coins", "Mine Coins", "Mine Large Coins", "Mine Tiny Coins", "Desert Coins", "Desert Large Coins", "Desert Tiny Coins", "Volcano Coins", "Volcano Large Coins", "Volcano Tiny Coins", "Winter Coins", "Winter Large Coins", "Winter Tiny Coins", "Glacier Coins", "Glacier Large Coins", "Glacier Tiny Coins", "Enchanted Forest Coins", "Enchanted Forest Large Coins", "Enchanted Forest Tiny Coins", "Ancient Island Coins", "Ancient Island Large Coins", "Ancient Island Tiny Coins", "Samurai Island Coins", "Samurai Island Large Coins", "Samurai Island Tiny Coins", "Candy Island Coins", "Candy Island Large Coins", "Candy Island Tiny Coins", "Haunted Island Coins", 'Haunted Island Large Coins', 'Haunted Island Tiny Coins', 'Heaven Island Coins', 'Heaven Island Large Coins', 'Heaven Island Tiny Coins', 'Tech City Coins', 'Tech City Large Coins', 'Tech City Tiny Coins', 'Dark Tech Coins', 'Dark Tech Large Coins', 'Dark Tech Tiny Coins', 'Steampunk Coins', 'Steampunk Large Coins', 'Steampunk Tiny Coins', 'Alien Lab Coins', 'Alien Lab Large Coins', 'Alien Lab Tiny Coins', 'Alien Forest Coins', 'Alien Forest Large Coins', 'Alien Forest Tiny Coins', 'Blue Glitched Coins', 'Blue Glitched Large Coins', 'Blue Glitched Tiny Coins', 'Pink Glitched Coins', 'Pink Glitched Large Coins', 'Pink Glitched Tiny Coins', 'Axolotl Ocean Coins', 'Axolotl Ocean Large Coins', 'Axolotl Ocean Tiny Coins', 'Pixel Forest Coins', 'Pixel Forest Large Coins', 'Pixel Forest Tiny Coins', 'Pixel Kyoto Coins', 'Pixel Kyoto Large Coins'}

local ChestsMasteryList = {'Town Chest', "Forest Small Chest", "Forest Chest", "Beach Chest", "Beach Small Chest", "Mine Small Chest", "Mine Chest", "Desert Chest", "Desert Small Chest", "Winter Chest", "Winter Small Chest", "Glacier Chest", "Glacier Small Chest", "Enchanted Forest Chest", "Enchanted Forest Small Chest", "Samurai Island Chest", "Samurai Island Small Chest", "Candy Island Chest", "Candy Island Small Chest", "Hell Island Chest", 'Hell Island Small Chest', "Heaven Island Chest", 'Heaven Island Small Chest', "Axolotl Deep Ocean Chest", "Axolotl Deep Ocean Small Chest", "Pixel Forest Chest", 'Pixel Forest Small Chest', "Pixel Alps Chest", 'Pixel Alps Small Chest'}

local PresentsMasteryList = {"Town Present", "Forest Present", "Beach Present", "Mine Present", "Desert Present", "Volcano Present", "Winter Present", "Glacier Present", "Enchanted Forest Present", "Ancient Island Present", "Samurai Island Present", "Candy Island Present", "Haunted Island Present", "Hell Island Present", "Heaven Island Present", "Tech City Present", "Dark Tech Present", "Alien Forest Present", "Blue Glitched Present", "Pink Glitched Present", "Axolotl Ocean Present", "Pixel Forest Present", "Pixel Kyoto Present", "Pixel Kyoto Large Present"}

local VaultsSafesMasteryList = {"Forest Safe", "Forest Vault", "Beach Safe", "Beach Vault", "Mine Safe", "Mine Vault", "Desert Safe", "Desert Vault", "Volcano Safe", "Volcano Vault", "Winter Safe", "Winter Vault", "Glacier Safe", "Glacier Vault", "Enchanted Forest Safe", "Enchanted Forest Vault", "Ancient Island Vault", 'Ancient Island Safe', "Candy Island Vault", 'Candy Island Safe', "Haunted Island Vault", 'Haunted Island Safe', "Heaven Island Vault", 'Heaven Island Safe', "Tech City Vault", 'Tech City Safe', "Steampunk Vault", 'Steampunk Safe', "Alien Lab Vault", 'Alien Lab Safe', "Blue Glitched Vault", 'Blue Glitched Safe', "Pink Glitched Vault", 'Pink Glitched Safe', "Axolotl Deep Ocean Vault", 'Axolotl Deep Ocean Safe', "Pixel Forest Vault", 'Pixel Forest Safe', "Pixel Vault Safe", "Pixel Vault Vault"}

local DiamondsMasteryList = {"Diamonds", "Tiny Diamonds"}

local EasterEggsList = {"Easter Egg", "Easter Egg Uncommon", "Easter Egg Rare", "Easter Egg Legendary"}

local MasteryIndex = {"Coins Piles Mastery", "Crates Mastery", "Chests Mastery", "Presents Mastery", "Vaults & Safes Mastery", "Diamonds Mastery"}

-----------------------------------------------

local SectionEvent = Tab:Section{
    Name = "Easter Egg Farm"
}

SectionEvent:Toggle{
    Name = "World Hopper",
    StartingState = false,
    Callback = function(whopfunc)
        _G.whop = whopfunc
        while _G.whop and task.wait() do
            EventWHopper()
        end
    end
}

SectionEvent:Slider{
    Name = "World Hopper Delay",
	Default = 75,
	Min = 30,
	Max = 90,
	Callback = function(whopwait) 
        _G.whopDelay = whopwait
    end
}

SectionEvent:Toggle{
    Name = "Easter Egg (Multi)",
    StartingState = false,
    Callback = function(EggFarmfunc)
        _G.EasterTog = EggFarmfunc
        while _G.EasterTog do
        local CurrentFarmingPets = {}
        local pethingy = GetMyPets()
        for i,v in pairs(EggFarm()) do
            if v.index%#pethingy == #pethingy-1 then wait() end
            if not CurrentFarmingPets[pethingy[v.index%#pethingy+1]] or CurrentFarmingPets[pethingy[v.index%#pethingy+1]] == nil then
                if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                    pcall(function()
                        CurrentFarmingPets[pethingy[v.index%#pethingy+1]] = 'Farming'
                        FarmCoin(v.index, pethingy[v.index%#pethingy+1])
                    end)
                end
            end
        end
        end
    end
}

SectionEvent:Toggle{
    Name = "Easter Egg (Normal)",
    StartingState = false,
    Callback = function(EggFarm2func)
        _G.EggFarm2 = EggFarm2func
        local CurrentFarmingPets = {}
        while _G.EggFarm2 do
            local pethingy = GetMyPets()
            for i,v in pairs(EggEvent()) do
                if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                    for a,b in pairs(pethingy) do
                        coroutine.wrap(function()
                            FarmCoin(v.index, b)
                        end)()
                    end
                    repeat task.wait() until not v.index or not game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) or not _G.EggFarm2
                end
            end
        end
    end
}

local SectionMastery = Tab:Section{
    Name = "Mastery Farm"
}

SectionMastery:Dropdown{
    Name = "Mastery List", 
    Items = MasteryIndex, 
    Callback = function(v)
    _G.MasteryList = v
    end
}

SectionMastery:Toggle{
    Name = "Auto Farm Mastery", 
    StartingState = false, 
    Callback = function(masteryfunc)
    _G.Mastery = masteryfunc
    while _G.Mastery do
        if _G.MasteryList == "Crates Mastery" then
            local CurrentFarmingPets = {}
            local pethingy = GetMyPets()
            for i,v in pairs(CratesMastery()) do
                if v.index%#pethingy == #pethingy-1 then wait() end
                if not CurrentFarmingPets[pethingy[v.index%#pethingy+1]] or CurrentFarmingPets[pethingy[v.index%#pethingy+1]] == nil then
                    if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                        pcall(function()
                            CurrentFarmingPets[pethingy[v.index%#pethingy+1]] = 'Farming'
                            FarmCoin(v.index, pethingy[v.index%#pethingy+1])
                        end)
                    end
                end
            end
        elseif _G.MasteryList == "Coins Piles Mastery" then
            local CurrentFarmingPets = {}
            local pethingy = GetMyPets()
            for i,v in pairs(CoinsPilesMastery()) do
                if v.index%#pethingy == #pethingy-1 then wait() end
                if not CurrentFarmingPets[pethingy[v.index%#pethingy+1]] or CurrentFarmingPets[pethingy[v.index%#pethingy+1]] == nil then
                    if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                        pcall(function()
                            CurrentFarmingPets[pethingy[v.index%#pethingy+1]] = 'Farming'
                            FarmCoin(v.index, pethingy[v.index%#pethingy+1])
                        end)
                    end
                end
            end
        elseif _G.MasteryList == "Chests Mastery" then
            local CurrentFarmingPets = {}
            local pethingy = GetMyPets()
            for i,v in pairs(ChestsMastery()) do
                if v.index%#pethingy == #pethingy-1 then wait() end
                if not CurrentFarmingPets[pethingy[v.index%#pethingy+1]] or CurrentFarmingPets[pethingy[v.index%#pethingy+1]] == nil then
                    if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                        pcall(function()
                            CurrentFarmingPets[pethingy[v.index%#pethingy+1]] = 'Farming'
                            FarmCoin(v.index, pethingy[v.index%#pethingy+1])
                        end)
                    end
                end
            end
        elseif _G.MasteryList == "Presents Mastery" then
            local CurrentFarmingPets = {}
            local pethingy = GetMyPets()
            for i,v in pairs(PresentsMastery()) do
                if v.index%#pethingy == #pethingy-1 then wait() end
                if not CurrentFarmingPets[pethingy[v.index%#pethingy+1]] or CurrentFarmingPets[pethingy[v.index%#pethingy+1]] == nil then
                    if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                        pcall(function()
                            CurrentFarmingPets[pethingy[v.index%#pethingy+1]] = 'Farming'
                            FarmCoin(v.index, pethingy[v.index%#pethingy+1])
                        end)
                    end
                end
            end
        elseif _G.MasteryList == "Vaults & Safes Mastery" then
            local CurrentFarmingPets = {}
            local pethingy = GetMyPets()
            for i,v in pairs(VaultsSafesMastery()) do
                if v.index%#pethingy == #pethingy-1 then wait() end
                if not CurrentFarmingPets[pethingy[v.index%#pethingy+1]] or CurrentFarmingPets[pethingy[v.index%#pethingy+1]] == nil then
                    if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                        pcall(function()
                            CurrentFarmingPets[pethingy[v.index%#pethingy+1]] = 'Farming'
                            FarmCoin(v.index, pethingy[v.index%#pethingy+1])
                        end)
                    end
                end
            end
        elseif _G.MasteryList == "Diamonds Mastery" then
            local CurrentFarmingPets = {}
            local pethingy = GetMyPets()
            for i,v in pairs(DiamondsMastery()) do
                if v.index%#pethingy == #pethingy-1 then wait() end
                if not CurrentFarmingPets[pethingy[v.index%#pethingy+1]] or CurrentFarmingPets[pethingy[v.index%#pethingy+1]] == nil then
                    if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                        pcall(function()
                            CurrentFarmingPets[pethingy[v.index%#pethingy+1]] = 'Farming'
                            FarmCoin(v.index, pethingy[v.index%#pethingy+1])
                        end)
                    end
                end
            end
        else
            wait()
        end
    end
end
}

function EggFarm()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(EasterEggsList) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(EasterEggsList, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end

function CratesMastery()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(CratesMasteryList) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(CratesMasteryList, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end

function CoinsPilesMastery()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(CoinsPilesMasteryList) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(CoinsPilesMasteryList, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end

function ChestsMastery()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(ChestsMasteryList) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(ChestsMasteryList, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end

function PresentsMastery()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(PresentsMasteryList) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(PresentsMasteryList, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end

function VaultsSafesMastery()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(VaultsSafesMasteryList) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(VaultsSafesMasteryList, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end

function DiamondsMastery()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(DiamondsMasteryList) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(DiamondsMasteryList, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end

function EggEvent()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(EasterEggsList) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(EasterEggsList, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end
--------------------------------------------------------------------------------
local Library = require(game:GetService("ReplicatedStorage").Framework.Library)
local Network = Library.Network
local rs = RunService.RenderStepped
local IDToName = {}
local NameToID = {}
for i,v in pairs(Library.Directory.Pets) do
    IDToName[i] = v.name
    NameToID[v.name] = i
end

_G.whopDelay = 75

function EventWHopper()
    local Worlds = {"Spawn", "Fantasy", "Tech", "Axolotl Ocean", "Pixel"}
    if _G.EggFarm2 or _G.EasterTog then
        for hh,jj in pairs(Worlds) do
            Library.WorldCmds.Load(jj)
            task.wait(_G.whopDelay)
            if _G.whop == false then
                repeat wait() until _G.whop == true
                break
            end
            if _G.EggFarm2 == false then
                break
            end
            if _G.EasterTog == false then
                break
            end
            task.wait(2)
        end
    end
end

function AllChests()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(Chests) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(Chests, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end

function GetMyPets()
   local returntable = {}
   for i,v in pairs(Library.Save.Get().Pets) do
       if v.e then 
           table.insert(returntable, v.uid)
       end
   end
   return returntable
end

function FarmCoin(CoinID, PetID)
    game.workspace['__THINGS']['__REMOTES']["join coin"]:InvokeServer({[1] = CoinID, [2] = {[1] = PetID}})
    game.workspace['__THINGS']['__REMOTES']["farm coin"]:FireServer({[1] = CoinID, [2] = PetID})
end

function GetCoinsNormal(area)
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        if string.lower(v.a) == string.lower(area) then
            table.insert(returntable, i)
        end
    end
    return returntable
end
        
function GetCoins(area, exclude)
    exclude = exclude or {}
    local Areas = (IMightKillMyselfCauseOfThis)
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        if _G.AreaFarm == "All" or table.find(Areas[_G.AreaFarm], v.a) and not table.find(exclude, v.n) then
            local shit = v
            shit["index"] = i
            table.insert(returntable, shit)
         end
    end
    return returntable
end

function GetCoinTable(area, Type, exclude)
    exclude = exclude or {}
    local CoinTable = GetCoins(area, exclude)
    local function getKeysSortedByValue(tbl, sortFunction)
        local keys = {}
        for key in pairs(tbl) do
            table.insert(keys, key)
        end
        table.sort(keys, function(a, b)
            return sortFunction(tbl[a].h, tbl[b].h)
        end)
        return keys
    end
    local sortedKeys
    if Type == 'Highest' then
        sortedKeys = getKeysSortedByValue(CoinTable, function(a, b) return a > b end)
    elseif Type == 'Lowest' then
        sortedKeys = getKeysSortedByValue(CoinTable, function(a, b) return a < b end)
    end
    local newCoinTable = {}
    for i,v in pairs(sortedKeys) do
        table.insert(newCoinTable, CoinTable[v])
    end
    return newCoinTable
end

if _G.MyConnection then
    _G.MyConnection:Disconnect()
end
_G.MyConnection = game.Workspace.__THINGS.Orbs.ChildAdded:Connect(function(Orb)
    game.Workspace.__THINGS.__REMOTES["claim orbs"]:FireServer({{Orb.Name}})
    Orb.Name:Destroy()
end)

local PixelList = {"Pixel Vault Vault", "Pixel Vault Safe"}

function PixelVaultAreas()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        local shit = v
        shit["index"] = i
        for aa,bb in pairs(PixelList) do
            if string.find(v.n, bb) then
                local thing = string.gsub(v.n, bb.." ", " ")
                if table.find(PixelList, thing) then
                    shit.n = thing
                    table.insert(returntable, shit)
                end
            end
        end
    end
    return returntable
end
function PixelAreasss()
    local returntable = {}
    local ListCoins = game.workspace['__THINGS']['__REMOTES']["get coins"]:InvokeServer({})[1]
    for i,v in pairs(ListCoins) do
        if v.Name == "Pixel Vault Vault" or v.Name == "Pixel Vault Safe" then
            table.insert(returntable, i)
        end
    end
    return returntable
end
---------------------------------------------------------------------------------

local SectionPV = Tab:Section{
    Name = "Pixel Vault Farm"
}

SectionPV:Toggle{
    Name = "Pixel Vault (Multi)",
    StartingState = false,
    Callback = function(pixelmultifunc)
        _G.PixelVault = pixelmultifunc
        while _G.PixelVault do
            local CurrentFarmingPets = {}
            local pethingy = GetMyPets()
            for i,v in pairs(PixelVaultAreas()) do
                if v.index%#pethingy == #pethingy-1 then wait() end
                if not CurrentFarmingPets[pethingy[v.index%#pethingy+1]] or CurrentFarmingPets[pethingy[v.index%#pethingy+1]] == nil then
                    if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                        pcall(function()
                            CurrentFarmingPets[pethingy[v.index%#pethingy+1]] = 'Farming'
                            FarmCoin(v.index, pethingy[v.index%#pethingy+1])
                        end)
                    end
                end
            end
        end
    end
}

SectionPV:Toggle{
    Name = "Pixel Vault (Normal)",
    Description = "Use this method if you have low stat pet",
    StartingState = false,
    Callback = function(pixelnormfunc)
        _G.PixelVault2 = pixelnormfunc
        local CurrentFarmingPets = {}
        while _G.PixelVault2 do
            local pethingy = GetMyPets()
            for i,v in pairs(PixelVaultAreas()) do
                if game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) then
                    for a,b in pairs(pethingy) do
                        coroutine.wrap(function()
                            FarmCoin(v.index, b)
                        end)()
                    end
                    repeat task.wait() until not v.index or not game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) or not _G.PixelVault2
                end
            end
        end
    end
}

local SectionCoin = Tab:Section{
    Name = "Coin Farm"
}

SectionCoin:Dropdown{
    Name = "Select Area List", 
    Items = AreaList, 
    Callback = function(areafunc)
    _G.AreaFarm = areafunc
    end
}

SectionCoin:Toggle{
    Name = "Multi Target",
    StartingState = false,
    Callback = function(multi1func)
        _G.MultiTarget1 = multi1func
        local CurrentFarmingPets = {}
        while _G.MultiTarget1 do
            local pethingy = GetMyPets()
            local cointhiny = GetCoins(_G.AreaFarm)
            for i = 1, #cointhiny do
                if i%#pethingy == #pethingy-1 then wait() end
                if not CurrentFarmingPets[pethingy[i%#pethingy+1]] or CurrentFarmingPets[pethingy[i%#pethingy+1]] == nil then
                    spawn(function()
                        CurrentFarmingPets[pethingy[i%#pethingy+1]] = 'Farming'
                        FarmCoin(cointhiny[i].index, pethingy[i%#pethingy+1])
                        repeat task.wait() until not game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(cointhiny[i].index) or #game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(cointhiny[i].index).Pets:GetChildren() == 0
                        CurrentFarmingPets[pethingy[i%#pethingy+1]] = nil
                    end)
                end
            end
        end
    end
}

SectionCoin:Toggle{
    Name = "Multi Target 2",
    StartingState = false,
    Callback = function(multi2func)
        _G.MultiTarget2 = multi2func
        while _G.MultiTarget2 do
            local pethingy = GetMyPets()
            local cointhiny = GetCoinsNormal(_G.AreaFarm)
            for i = 1, #cointhiny do
                pcall(function()
                    FarmCoin(cointhiny[i], pethingy[i%#pethingy+1])
                end)
            end
        end
    end
}

SectionCoin:Toggle{
    Name = "Low Value (Priority)",
    StartingState = false,
    Callback = function(lowprio)
        _G.LowVal = lowprio
        local CurrentFarmingPets = {}
        while _G.LowVal do
            local pethingy = GetMyPets()
            local cointhiny = GetCoinTable(_G.AreaFarm, 'Lowest')
            for i = 1, (#cointhiny >= #pethingy and #pethingy or #cointhiny) do
                if not CurrentFarmingPets[pethingy[i%#pethingy+1]] or CurrentFarmingPets[pethingy[i%#pethingy+1]] == nil then
                    coroutine.wrap(function()
                        CurrentFarmingPets[pethingy[i%#pethingy+1]] = 'Farming'
                        FarmCoin(cointhiny[i].index, pethingy[i%#pethingy+1])
                        repeat task.wait(0.0001) until not game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(cointhiny[i].index) or #game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(cointhiny[i].index).Pets:GetChildren() == 0 or not _G.LowVal
                        CurrentFarmingPets[pethingy[i%#pethingy+1]] = nil
                    end)()
                end
            end
        end
    end
}

SectionCoin:Toggle{
    Name = "High Value (Priority)",
    StartingState = false,
    Callback = function(highprio)
        _G.HighVal = highprio
        local CurrentFarmingPets = {}
        while _G.HighVal do
            local pethingy = GetMyPets()
            local cointhiny = GetCoinTable(_G.AreaFarm, 'Highest')
            if #cointhiny >= 3 then
                local CurrentFarmingPets = {}
                for a = 1, 3 do
                    coroutine.wrap(function()
                        if CurrentFarmingPets[a] == nil then
                            for petnum = a, #pethingy, 3 do
                                coroutine.wrap(function()
                                    if not CurrentFarmingPets[a] then CurrentFarmingPets[a] = {} end
                                    if CurrentFarmingPets[a] ~= nil and game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(cointhiny[a].index) and not table.find(CurrentFarmingPets[a], pethingy[petnum]) then
                                        table.insert(CurrentFarmingPets[a], pethingy[petnum])
                                        FarmCoin(cointhiny[a].index, pethingy[petnum]) 
                                    end
                                end)()
                            end
                            repeat task.wait(0.001) until not game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(cointhiny[a].index) or #game:GetService("Workspace")["__THINGS"].Coins[cointhiny[a].index].Pets:GetChildren() == 0  or not _G.HighVal
                            CurrentFarmingPets[a] = nil
                        end
                    end)()
                end
            else
                 task.wait()
            end
        end
    end
}

SectionCoin:Toggle{
    Name = "Normal", 
    StartingState = false, 
    Callback = function(farmnormfunc)
    _G.FarmNorm = farmnormfunc
    local CurrentFarmingPets = {}
    while _G.FarmNorm do
        local pethingy = GetMyPets ()
        local cointhiny = GetCoins(_G.AreaFarm)
        for i = 1, #cointhiny do
            if _G.FarmNorm and game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(cointhiny[i].index) then
                for _, bb in pairs(pethingy) do
                    coroutine.wrap(function()
                        FarmCoin(cointhiny[i].index, bb)
                    end)()
                end
                repeat task.wait(0.001) until not game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(cointhiny[i].index) or not _G.FarmNorm
            end
        end
    end
end
}

SectionCoin:Toggle{
    Name = "Nearest", 
    StartingState = false, 
    Callback = function(nearfunc)
    _G.NearestF = nearfunc
    local CurrentFarmingPets = {}
    while _G.NearestF do
        local pethingy = GetMyPets()
        local cointhiny = nil
        local cointable = game:GetService("Workspace")["__THINGS"].Coins:GetChildren()
        table.sort(cointable, function(i, v)
            return (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - i.POS.Position).magnitude < (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.POS.Position).magnitude
        end)
        local NearestOne = cointable[1]
        if NearestOne ~= nil then
            for a,b in pairs(pethingy) do
                coroutine.wrap(function()
                    if NearestOne ~= nil then
                        FarmCoin(NearestOne.Name, b)
                    end
                end)()
            end
            repeat task.wait(0.001) until not game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(NearestOne.Name) or #game:GetService("Workspace")["__THINGS"].Coins[NearestOne.Name].Pets:GetChildren() == 0
                else
                    task.wait()
        end
    end
end
}

local SectionChest = Tab:Section{
    Name = "Chest Farm"
}

SectionChest:Dropdown{
    Name = "Chest List", 
    Items = Chests, 
    Callback = function(chestlistfunc)
    _G.ListChest = chestlistfunc
end
}

SectionChest:Toggle{
    Name = "Chest Farm", 
    StartingState = false, 
    Callback = function(chestfunc)
    _G.ChestFarm = chestfunc
    local CurrentFarmingPets = {}
    while _G.ChestFarm do
        local pethingy = GetMyPets()
        for i,v in pairs(AllChests()) do
            if (v.n == _G.ListChest) or (_G.ListChest == 'All') then
                local StartTick = tick()
                for a,b in pairs(pethingy) do
                    coroutine.wrap(function()
                        FarmCoin(v.index, b)
                        tick(StartTick)
                        repeat task.wait() until not game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index) or #game:GetService("Workspace")["__THINGS"].Coins:FindFirstChild(v.index).Pets:GetChildren() == 0 or tick() > StartTick + 1 or not _G.ChestFarm
                    end)()
                end
            end
        end
    end
end
}

local TabEgg = GUI:Tab{
    Name = "Eggs",
    Icon = "rbxassetid://8825651806"
}

workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "buy egg")

-- Eggs
local EggData = {}
local ListEgg = game:GetService("ReplicatedStorage").Game.Eggs
for i,v in pairs(ListEgg:GetChildren()) do
    if v.Name == 'Pixel Eggs' or v.Name == 'Axolotl Ocean' or v.Name == 'Tech Eggs' or v.Name == 'Fantasy Eggs' or v.Name == 'Spawn Eggs' or v.Name == 'Other' then
        table.insert(EggData, "-- " .. v.Name .. " World --")
        for aa,bb in pairs(v:GetChildren()) do
            if v.Name == 'Pixel Eggs' or v.Name == 'Axolotl Ocean' or v.Name == 'Tech Eggs' or v.Name == 'Fantasy Eggs' or v.Name == 'Spawn Eggs' or v.Name == 'Other' then
                table.insert(EggData, bb.Name)
            end
        end
    end
end

TabEgg:Dropdown{
    Name = "Select Eggs", 
    Items = EggData, 
    Callback = function(egglistfunc)
    _G.SelectEgg = egglistfunc
end
}

TabEgg:Toggle{
    Name = "Remove Egg Animation",
    Description = "Removes egg anim while opening eggs",
    StartingState = false,
    Callback = function(EggAnimfunc)
        _G.EggAnim = EggAnimfunc
    end
}

TabEgg:Toggle{
    Name = "Clear Inventory Notification",
    Description = "Opens your inventory every seconds you set to clear notifcation",
    StartingState = false,
    Callback = function(ClearInventoryfunc)
        _G.ClearInventory = ClearInventoryfunc
    end
}

TabEgg:Slider{
    Name = "Clear Inventory Notif Delay",
    Description = "Default: 180",
	Default = 180,
	Min = 60,
	Max = 900,
	Callback = function(CIwait) 
        _G.InvDelay = CIwait
    end
}

TabEgg:Toggle{
    Name = "Triple Eggs", 
    StartingState = false,
    Description = "You need gamepass for this",
    Callback = function(tripleeggfunc)
    _G.TripleEggs = tripleeggfunc
end
}

TabEgg:Slider{
    Name = "Egg Delay",
	Default = 0,
	Min = 0,
	Max = 10,
	Callback = function(Eggwait) 
        _G.EggDelay = Eggwait
    end
}

TabEgg:Textbox{
	Name = "Custom Wait Value",
    Description = "Use numbers only pls.",
	Callback = function(Val) 
        local converted = tonumber(Val)
        _G.EggDelay = converted
    end
}

TabEgg:Toggle{
    Name = "Open Eggs", 
    StartingState = false, 
    Callback = function(openeggsfunc)
    _G.OpenEgg = openeggsfunc
    while _G.OpenEgg do
        local Table1 = {
            [1] = _G.SelectEgg,
            [2] = _G.TripleEggs
        }
        Workspace.__THINGS.__REMOTES["buy egg"]:InvokeServer(Table1)
        wait(_G.EggDelay)
    end
end
}

_G.InvDelay = 180

spawn(function()
    while task.wait() do
        if _G.ClearInventory then
            wait(_G.InvDelay)
            game:GetService("Players").LocalPlayer.PlayerGui.Inventory.Enabled = true
            wait(1)
            game:GetService("Players").LocalPlayer.PlayerGui.Inventory.Enabled = false
        end
    end
end)
spawn(function()
    while task.wait() do
        if _G.EggAnim == true then
            game:GetService("Players").LocalPlayer.PlayerScripts.Scripts.Game["Open Eggs"].Disabled = true
        elseif _G.EggAnim == false then
            game:GetService("Players").LocalPlayer.PlayerScripts.Scripts.Game["Open Eggs"].Disabled = false
        end
    end
end)

local TabPets = GUI:Tab{
    Name = "Pets",
    Icon = "rbxassetid://8879573067"
}

-- // Service \\
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "convert to dark matter")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "use golden machine")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "use rainbow machine")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "use fuse pets machine")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "fuse pets")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "enchant pet")

local IDToName = {}
local NameToID = {}
local PettoRarity = {}
local RarityTable = {}
local PetNamesTable = {}
local PetNamesTable = {}
for i,v in pairs(Library.Directory.Pets) do
    IDToName[i] = v.name
    NameToID[v.name] = i
    PettoRarity[i] = v.rarity
    if not table.find(RarityTable, v.rarity) then
        table.insert(RarityTable, v.rarity)
    end
    table.insert(PetNamesTable, v.name)
end

function GetPets()
    local MyPets = {}
    for i,v in pairs(Library.Save.Get().Pets) do
        local ThingyThingyTempTypeThing = (v.g and 'Gold') or (v.r and 'Rainbow') or (v.dm and 'Dark Matter') or 'Normal'
        local TempString = ThingyThingyTempTypeThing .. IDToName[v.id]
        if MyPets[TempString] then
            table.insert(MyPets[TempString], v.uid)
        else
            MyPets[TempString] = {}
            table.insert(MyPets[TempString], v.uid)
        end
    end
    return MyPets
end

-- Enchant
local EnchantsList = {
    'Magnet',
    'Royalty',
    'Glittering',
    'Tech Coins',
    'Fantasy Coins',
    'Rainbow Coins',
    'Coins',
    'Teamwork',
    'Diamonds',
    'Strength',
    'Chests',
    'Presents',
    'Agility',
    'Charm'
}

local EnchantLevel = {1, 2, 3, 4, 5}

local PettoRarity = {}
local a = require(game:GetService("ReplicatedStorage").Framework.Modules["1 | Directory"].Pets["Grab All Pets"])
for i, v in pairs(a) do
    PettoRarity[i] = v.rarity
end
function GetPetTable(PetUID)
    for i, v in pairs(Library.Save.Get().Pets) do
        if v.uid == PetUID then
            return v
        end
    end
end
-----------------
local SectionEnchant = TabPets:Section{
    Name = "Enchant"
}


SectionEnchant:Dropdown{
    Name = "Enchant Type", 
    Items = EnchantsList, 
    Callback = function(enchantlistfunc)
    _G.EnchantType = enchantlistfunc
end
}

SectionEnchant:Dropdown{
    Name = "Enchant Level", 
    Items = EnchantLevel, 
    Callback = function(enchantlevelfunc)
    _G.Enchantlevel = enchantlevelfunc
end
}

SectionEnchant:Toggle{
    Name = "Auto Enchant", 
    StartingState = false, 
    Description = "Enchant your equip pets",
    Callback = function(enchantfunc)
    _G.AutoEnchant = enchantfunc
    local Wanted = {
        [_G.EnchantType] = _G.Enchantlevel or 1;
    }
    while wait() and _G.AutoEnchant do
        for i, v in pairs(Library.Save.Get().Pets) do
            if v.e and PettoRarity[v.id] ~= 'Mythical' and _G.AutoEnchant then
                local haspower = false
                repeat
                    if GetPetTable(v.uid).powers then
                        for i2, v2 in pairs(GetPetTable(v.uid).powers) do
                            warn(v2[1], v2[2])
                            print(Wanted[v2[1]])
                            if Wanted[v2[1]] ~= nil and not haspower then
                                if Wanted[v2[1]] <= v2[2] then
                                    haspower = true
                                    warn("Pet", v.uid, "has", v2[1], v2[2])
                                end
                            end
                        end
                        if not haspower then
                            print("Yea we kinda need new enchantments on", v.uid)
                            workspace.__THINGS.__REMOTES["enchant pet"]:InvokeServer({[1] = v.uid})
                        end
                    else
                        warn("taking", v.uid,'\'s enchanting virginity lol')
                        workspace.__THINGS.__REMOTES["enchant pet"]:InvokeServer({[1] = v.uid})
                    end
                until haspower == true or Library.Save.Get().Diamonds < 10000 or _G.AutoEnchant == false
            end
        end
    end
end
}

local SectionPetGR = TabPets:Section{
    Name = "Gold/Rainbow"
}
-----------------------------------
local PetCount = {1, 2, 3, 4, 5, 6}
-----------------------------------

SectionPetGR:Dropdown{
    Name = "Select Amount", 
    Items = PetCount, 
    Callback = function(amountgrfunc)
    _G.ValuePets = amountgrfunc
end
}

SectionPetGR:Toggle{
    Name = "Auto Golden Pets", 
    StartingState = false, 
    Callback = function(goldenfunc)
    _G.AutoGold = goldenfunc
    while wait() and _G.AutoGold do
        for i,v in pairs(GetPets()) do
            if #v >= _G.ValuePets and _G.AutoGold then
                if string.find(i, "Normal") and _G.AutoGold then
                    local Args = {}
                    for eeeee = 1, _G.ValuePets do
                        Args[#Args+1] = v[#Args+1]
                    end
                    workspace.__THINGS.__REMOTES["use golden machine"]:InvokeServer({Args})
                end
            end
        end
    end
end
}

SectionPetGR:Toggle{
    Name = "Auto Rainbow Pets", 
    StartingState = false, 
    Callback = function(raibowfunc)
    _G.AutoRainbow = raibowfunc
    while wait() and _G.AutoRainbow do
        for i,v in pairs(GetPets()) do
            if #v >= _G.ValuePets and _G.AutoRainbow then
                if string.find(i, "Gold") and _G.AutoRainbow then
                    local Args = {}
                    for eeeee = 1, _G.ValuePets do
                        Args[#Args+1] = v[#Args+1]
                    end
                    workspace.__THINGS.__REMOTES["use rainbow machine"]:InvokeServer({Args})
                end
            end
        end
    end
end
}

local SectionDM = TabPets:Section{
    Name = "Dark Matter"
}

--[[SectionDM:TextBox{
    Name = "Enter Pets Name", 
    Placeholder = "Type Here..", 
    Callback = function(dmnamefunc)
    _G.NameOfPet = dmnamefunc
end
}]]

SectionDM:Dropdown{
    Name = "Select Amount", 
    Items = PetCount, 
    Callback = function(dmvalfunc)
    _G.CountDarkMatterFunc1 = dmvalfunc
end
}

SectionDM:Toggle{
    Name = "Auto Dark Matter", 
    StartingState = false,
    Callback = function(dmfunc)
    _G.AutoMakeDarkMatter = dmfunc
    while task.wait() and _G.AutoMakeDarkMatter do
        local Save = Library.Save.Get()
        local Slots = Save.DarkMatterSlots
        local Queued = 0
        for a, b in pairs(Save.DarkMatterQueue) do
            Queued = Queued + 1 
        end
        local Slots = Slots - Queued
        for count = 1, Slots do
            if Slots - count >= 0 then
                local PetList = {}
                for i,v in pairs(Library.Save.Get().Pets) do
                    if v.e == true then --Check if equipped
                        continue
                    end
                    if #PetList < _G.CountDarkMatterFunc1 and v.r then
                        table.insert(PetList, v.uid)
                    else
                        break
                    end
                end
                if #PetList >= _G.CountDarkMatterFunc1 then
                    local tablething = {[1] = {}}
                    for eeek = 1, _G.CountDarkMatterFunc1 do
                        tablething[1][eeek] = PetList[eeek]
                    end
                    workspace.__THINGS.__REMOTES["convert to dark matter"]:InvokeServer(tablething)
                end
            end 
        end
        task.wait()
    end
end
}

SectionDM:Toggle{
    Name = "Auto Claim Dark Matters", 
    StartingState = false, 
    Callback = function(dmclaimfunc)
    _G.AutoClaimDarkMatter = dmclaimfunc
    while task.wait() and _G.AutoClaimDarkMatter do
        for i,v in pairs(Library.Save.Get().DarkMatterQueue) do
            if math.floor(v.readyTime - os.time()) < 0 then
                workspace.__THINGS.__REMOTES["redeem dark matter pet"]:InvokeServer({[1] = i})
            end
            task.wait()
        end
    end
end
}

local SectionFuse = TabPets:Section{
    Name = "Fuse"
}

SectionFuse:Slider{
    Name = "Fuse Amount",
    Default = 3,
    Min = 3,
    Max = 12,
    Callback = function(FuseValfunc)
        _G.FuseVal = FuseValfunc
    end
}

SectionFuse:Toggle{
    Name = "Auto Fuse",
    StartingState = false,
    Description = "Automatically fuse your unequipped pets",
    Callback = function(Fusefunc)
        _G.AutoFuse = Fusefunc
        while task.wait() and _G.AutoFuse do
            local Save = Library.Save.Get()
            local Pets = Save.Pets
            local SelectPet = {}
            for i=1,#Pets do
                local v = Pets[i]
                if v.e == true then --Check if equipped
                    continue
                end
                if #SelectPet < _G.FuseVal then
                    table.insert(SelectPet,v.uid)
                else
                    break
                end
            end
            if #SelectPet == _G.FuseVal then
                Library.Network.Invoke("Fuse Pets",SelectPet)
            end
        end
    end
}

local SectionRN = TabPets:Section{
    Name = "Rename"
}

SectionRN:Textbox{
	Name = "Pet Name",
    Placeholder = "Type Here..",
    Description = "Press enter after you type the name you want",
	Callback = function(PetString) 
        _G.PetName = PetString
    end
}

SectionRN:Button{
	Name = "Change Name",
	Description = "Changes your current equipped pets name",
	Callback = function() 
        local pethingy = GetMyPets()

        for a,b in pairs(pethingy) do
            local args = {
                [1] = {
                    [1] = b,
                    [2] = _G.PetName
                }
            }
    
            workspace.__THINGS.__REMOTES:FindFirstChild("rename pet"):InvokeServer(unpack(args))
            wait(1.5)
        end
    end
}

SectionRN:Toggle{
    Name = "Rick Roll Rename",
    StartingState = false,
    Description = "Rick Astley song (It is recommended on single pet only)",
    Callback = function (RRtog)
        local RRLyrics = {
            "Never gonna",
            "give you up",
            "Never gonna",
            "let you down",
            "Never gonna",
            "run around",
            "and desert u",
            "Never gonna",
            "make you cry",
            "Never gonna",
            "say goodbye",
            "Never gonna",
            "tell a lie",
            "and",
            "hurt",
            "ẙ☼υ",
            "Rick Astley"
        }
        _G.RickRollin = RRtog
        while task.wait() and _G.RickRollin do
            local pethingy = GetMyPets()

            for a,b in pairs(pethingy) do
                for r,l in pairs(RRLyrics) do
                    local args = {
                        [1] = {
                            [1] = b,
                            [2] = l
                        }
                    }
            
                    workspace.__THINGS.__REMOTES:FindFirstChild("rename pet"):InvokeServer(unpack(args))
                    wait(0.5)
                end
            end
        end
    end
}

local TabMisc = GUI:Tab{
    Name = "Miscellaneous",
    Icon = "rbxassetid://9209102664"
}
-- // Service \\
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "get merchant items")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "buy merchant item")
workspace.__THINGS.__REMOTES.MAIN:FireServer("a", "Merchant Arrival")

local SectionMerch = TabMisc:Section{
    Name = "Merchant"
}

SectionMerch:Toggle{
    Name = "Auto Buy Merchant [Tier 1]", 
    StartingState = false, 
    Callback = function(merchant1func)
    _G.m1 = merchant1func
    while task.wait() do
        if _G.m1 then
            if game:GetService("Players").LocalPlayer.PlayerGui.Merchant.Frame.Container:FindFirstChild("1") then
                workspace.__THINGS.__REMOTES["get merchant items"]:InvokeServer({[1] = "1"})
                wait(1)
                workspace.__THINGS.__REMOTES["buy merchant item"]:InvokeServer({1})
            end
        end
    end
end
}

SectionMerch:Toggle{
    Name = "Auto Buy Merchant [Tier 2]", 
    StartingState = false, 
    Callback = function(merchant2func)
        _G.m2 = merchant2func
        while task.wait() do
            if _G.m2 then
                if game:GetService("Players").LocalPlayer.PlayerGui.Merchant.Frame.Container:FindFirstChild("2") then
                    workspace.__THINGS.__REMOTES["get merchant items"]:InvokeServer({[2] = "2"})
                    wait(1)
                    workspace.__THINGS.__REMOTES["buy merchant item"]:InvokeServer({2})
                end
            end
        end
    end
}

SectionMerch:Toggle{
    Name = "Auto Buy Merchant [Tier 3]", 
    StartingState = false, 
    Callback = function(merchant3func)
        _G.m3 = merchant3func
        while task.wait() do
            if _G.m3 then
                if game:GetService("Players").LocalPlayer.PlayerGui.Merchant.Frame.Container:FindFirstChild("3") then
                    workspace.__THINGS.__REMOTES["get merchant items"]:InvokeServer({[3] = "3"})
                    wait(1)
                    workspace.__THINGS.__REMOTES["buy merchant item"]:InvokeServer({3})
                end
            end
        end
    end
}

SectionMerch:Button{
    Name = "Merchant GUI", 
    Callback = function()
    game:GetService("Players").LocalPlayer.PlayerGui.Merchant.Enabled = not game:GetService("Players").LocalPlayer.PlayerGui.Merchant.Enabled
end
}

local SectionRedeem = TabMisc:Section{
    Name = "Redeem"
}

-- // Service \\
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "redeem rank rewards")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "redeem vip rewards")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "redeem free gift")
workspace.__THINGS.__REMOTES.MAIN:FireServer("a", "activate boost")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "redeem dark matter pet")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "get my banks")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "get bank")
workspace.__THINGS.__REMOTES.MAIN:FireServer("b", "collect bank interest")

local bankAction = {}
bankAction.get = function(BUID)
    return Library.Network.Invoke("get bank", BUID)
end

local allBank = {}
local bankNames = {}
local selectedBankUID = nil

for i,v in pairs((Library.Network.Invoke("get my banks"))) do
    pcall(function ()
        name = Players:GetNameFromUserIdAsync(v.Owner)
    end)
    if name then
        allBank[name] = v.BUID
        table.insert(bankNames, name)
    end
end
-----------------------------------------------------------------------------
SectionRedeem:Toggle{
    Name = "Auto Redeem All Gifts Rewards", 
    StartingState = false, 
    Callback = function(giftfunc)
    _G.RedeemGift = giftfunc
    while task.wait() do 
        if _G.RedeemGift then
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({1})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({2})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({3})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({4})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({5})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({6})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({7})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({8})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({9})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({10})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({11})
            workspace.__THINGS.__REMOTES["redeem free gift"]:InvokeServer({12})
        end
    end
end
}

SectionRedeem:Toggle{
    Name = "Auto Redeem VIP/Ranks Rewards", 
    StartingState = false, 
    Callback = function(viprankfunc)
    _G.AutoRewards1 = viprankfunc
    while task.wait() do
        if _G.AutoRewards1 then
            workspace.__THINGS.__REMOTES["redeem vip rewards"]:InvokeServer({})
            workspace.__THINGS.__REMOTES["redeem rank rewards"]:InvokeServer({})
        end
    end
end
}

SectionRedeem:Toggle{
    Name = "Auto Redeem Bank Interest", 
    StartingState = false, 
    Callback = function(interestfunc)
    _G.AutoInterest = interestfunc
    while task.wait() do
        if _G.AutoInterest then
            local myBanks = (Library.Network.Invoke("get my banks"))
            for i,v in pairs(myBanks) do
                if(v.Owner == Library.LocalPlayer.UserId) then
                    bankIntrest = Library.Network.Invoke("collect bank interest", v.BUID)
                    bankDetail = Library.Network.Invoke("get bank", v.BUID)
                    wait((os.time() + 86400) - bankDetail.LastInterest)
                end
            end
        end
    end
end
}

local SectionBoost = TabMisc:Section{
    Name = "Boost"
}

SectionBoost:Toggle{
    Name = "Auto Boost Triple Damage", 
    StartingState = false,
    Description = "Automatically use the boost when the boost ended",
    Callback = function(tripdmgfunc)
    _G.Tripledmg = tripdmgfunc
end
}

SectionBoost:Toggle{
    Name = "Auto Boost Triple Coins", 
    StartingState = false, 
    Description = "Automatically use the boost when the boost ended",
    Callback = function(tripcoinfunc)
        _G.Triplecoins = tripcoinfunc
end
}

SectionBoost:Toggle{
    Name = "Auto Boost Super Lucky", 
    StartingState = false, 
    Description = "Automatically use the boost when the boost ended",
    Callback = function(superluckyfunc)
        _G.Superlucky = superluckyfunc
end
}

SectionBoost:Toggle{
    Name = "Auto Boost Ultra Lucky", 
    StartingState = false, 
    Description = "Automatically use the boost when the boost ended",
    Callback = function(ultraluckyfunc)
        _G.Ultralucky = ultraluckyfunc
end
}

spawn(function()
    local boost = game:GetService("Players").LocalPlayer.PlayerGui.Main.Boosts
    while task.wait() do
        if _G.Tripledmg then
            if not boost:FindFirstChild("Triple Damage") then
                workspace.__THINGS.__REMOTES["activate boost"]:FireServer({[1] = "Triple Damage"})
                repeat task.wait() until not _G.Tripledmg or boost:FindFirstChild("Triple Damage")
            end
        end
        if _G.Triplecoins then
            if not boost:FindFirstChild("Triple Coins") then
                workspace.__THINGS.__REMOTES["activate boost"]:FireServer({[1] = "Triple Coins"})
                repeat task.wait() until not _G.Triplecoins or boost:FindFirstChild("Triple Coins")
            end
        end
        if _G.Superlucky then
            if not boost:FindFirstChild("Super Lucky") then
                workspace.__THINGS.__REMOTES["activate boost"]:FireServer({[1] = "Super Lucky"})
                repeat task.wait() until not _G.Superlucky or boost:FindFirstChild("Super Lucky")
            end
        end
        if _G.Ultralucky then
            if not boost:FindFirstChild("Ultra Lucky") then
                workspace.__THINGS.__REMOTES["activate boost"]:FireServer({[1] = "Ultra Lucky"})
                repeat task.wait() until not _G.Ultralucky or boost:FindFirstChild("Ultra Lucky")
            end
        end
    end
end)

local SectionMods = TabMisc:Section{
    Name = "Mods"
}
local HoverboardsList = {"Original", "VIP", "Sleigh", "Flame", "Rainbow", "Cat", "Bling", "Blue Flying Carpet", "Red Flying Carpet"}

SectionMods:Dropdown{
    Name = "Hoverboards Skin", 
    Items = HoverboardsList, 
    Callback = function(hoverfunc)
    _G.Hovers = hoverfunc
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Sky2836/Sanz/main/Hoverboard"))()
end
}

SectionMods:Button{
    Name = "Unlock GamePasses", 
    Callback = function()
    local gmppath = require(game:GetService("ReplicatedStorage").Framework.Modules.Client["5 | Gamepasses"])
    gmppath.Owns = function() return true end
end
}

local SectionGuis = TabMisc:Section{
    Name = "GUI's"
}

SectionGuis:Button{
    Name = "Bank",
    Callback = function()
        game:GetService("Players").LocalPlayer.PlayerGui.Bank.Enabled = not game:GetService("Players").LocalPlayer.PlayerGui.Bank.Enabled
    end
}

SectionGuis:Button{
    Name = "Pet Collection",
    Callback = function()
        game:GetService("Players").LocalPlayer.PlayerGui.Collection.Enabled = not game:GetService("Players").LocalPlayer.PlayerGui.Collection.Enabled
    end
}

SectionGuis:Button{
    Name = "Fuse",
    Callback = function()
        game:GetService("Players").LocalPlayer.PlayerGui.FusePets.Enabled = not game:GetService("Players").LocalPlayer.PlayerGui.FusePets.Enabled
    end
}

SectionGuis:Button{
    Name = "Golden",
    Callback = function()
        game:GetService("Players").LocalPlayer.PlayerGui.Golden.Enabled = not game:GetService("Players").LocalPlayer.PlayerGui.Golden.Enabled
    end
}

SectionGuis:Button{
    Name = "Rainbow",
    Callback = function()
        game:GetService("Players").LocalPlayer.PlayerGui.Rainbow.Enabled = not game:GetService("Players").LocalPlayer.PlayerGui.Rainbow.Enabled
    end
}

SectionGuis:Button{
    Name = "Dark Matter",
    Callback = function()
        game:GetService("Players").LocalPlayer.PlayerGui.DarkMatter.Enabled = not game:GetService("Players").LocalPlayer.PlayerGui.DarkMatter.Enabled
    end
}

SectionGuis:Button{
    Name = "Enchant",
    Callback = function()
        game:GetService("Players").LocalPlayer.PlayerGui.EnchantPets.Enabled = not game:GetService("Players").LocalPlayer.PlayerGui.EnchantPets.Enabled
    end
}

local SectionClient = TabMisc:Section{
    Name = "Client Modification"
}

SectionClient:Button{
    Name = "FPS Boost",
    Callback = function()
        local decalsyeeted = true
        local g = game
        local w = g.Workspace
        local l = g.Lighting
        local t = w.Terrain
        t.WaterWaveSize = 0
        t.WaterWaveSpeed = 0
        t.WaterReflectance = 0
        t.WaterTransparency = 0
        l.GlobalShadows = false
        l.FogEnd = 9e9
        l.Brightness = 0
        settings().Rendering.QualityLevel = "Level01"
        for i, v in pairs(g:GetDescendants()) do
            if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then 
                v.Material = "Plastic"
                v.Reflectance = 0
            elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
                v.Transparency = 1
            elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
                v.Lifetime = NumberRange.new(0)
            elseif v:IsA("Explosion") then
                v.BlastPressure = 1
                v.BlastRadius = 1
            elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
                v.Enabled = false
            elseif v:IsA("MeshPart") then
                v.Material = "Plastic"
                v.Reflectance = 0
                v.TextureID = 10385902758728957
            end
        end
        for i, e in pairs(l:GetChildren()) do
            if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
                e.Enabled = false
            end
        end
    end
}

SectionClient:Button{
    Name = "Reduced lag [If Dropping fps]", 
    Callback = function()
    local a = game:GetService("Workspace")["__DEBRIS"]
    local b = a:Clone()
    b.Parent = a.Parent
    a:Destroy()
    for _,v in pairs(b:GetChildren()) do
        if v.Name == 'RewardBillboard' then
            v:Destroy()
        end
    end
end
}

enabledBefore = false
for i,v in pairs(game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui"):WaitForChild("Main"):WaitForChild("Right"):GetChildren()) do
    if v.Name:split('')[#v.Name] == '2' then
        enabledBefore = true
    end
end

SectionClient:Toggle{
    Name = "Stat Trackers",
    StartingState = false, 
    Callback = function(trackerfunc)
        _G.statTrackers = trackerfunc
        while wait() do
            if _G.statTrackers then
                if not enabledBefore then
                    loadstring(game:HttpGet("https://raw.githubusercontent.com/Sky2836/Sanz/main/StatTrack"))()
                    enabledBefore = true
                else
                    menus = game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui"):WaitForChild("Main"):WaitForChild("Right")
                    for i,v in pairs(menus:GetChildren()) do
                        if v.Name:split('')[#v.Name] == '2' then
                            v.Visible = true
                        end
                    end
                end
            else
                menus = game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui"):WaitForChild("Main"):WaitForChild("Right")
                for i,v in pairs(menus:GetChildren()) do
                    if v.Name:split('')[#v.Name] == '2' then
                        v.Visible = false
                    end
                end
            end
        end
    end
}

SectionClient:Slider{
    Name = "Inventory Size [Default 50]",
    Default = 50,
    Min = 50,
    Max = 200,
    Callback = function(value) 
        game:GetService("Players").LocalPlayer.PlayerGui.Inventory.Frame.Main.Pets.UIGridLayout.CellSize = UDim2.new(0, value, 0, value)
        game:GetService("Players").LocalPlayer.PlayerGui.Inventory.Frame.Main.Pets.UIGridLayout.CellPadding = UDim2.new(0, (value/3), 0, (value/3))
    end
}

local SectionPlayer = TabMisc:Section{
    Name = "Player Modification"
}

SectionPlayer:Slider{
    Name = "Walkspeed",
    Default = 26,
    Min = 16,
    Max = 260,
    Callback = function(val)
        game:GetService('Players').LocalPlayer.Character.Humanoid.WalkSpeed = val
    end
}

SectionPlayer:Slider{
    Name = "Jump",
    Default = 50,
    Min = 50,
    Max = 500,
    Callback = function(val)
        game:GetService('Players').LocalPlayer.Character.Humanoid.JumpPower = val
    end
}

function Depo()
    local lib = require(game.ReplicatedStorage:WaitForChild('Framework'):WaitForChild('Library')) 
    local mydiamonds = 0
    --local mybanks = lib.Network.Invoke("get my banks") 
    local PetsList = {} 
    for i,v in pairs(lib.Save.Get().Pets) do 
        local v2 = lib.Directory.Pets[v.id]; 
        if v2.rarity == "Basic" or v2.rarity == "Rare" or v2.rarity == "Epic" then 
            table.insert(PetsList, v.uid); 
        end 
    end
    
    local petstodep = {}
    
    for k,c in pairs(PetsList) do
        table.insert(petstodep, c)
        if k == 49 then
            lib.Network.Invoke("Bank Deposit", "c0324eb8-af8c-47b4-92f0-5c4763ea5415", petstodep, mydiamonds)
            break
        end
    end
end

local SectionBank = TabMisc:Section{
    Name = "Bank Function"
}

SectionBank:Toggle{
    Name = "Deposit Max Pet",
    Description = "Deposits Normal,Rare,Epic",
    Callback = function(DMPfunc)
        _G.StartDeposit = DMPfunc
        while _G.StartDeposit do
            Depo()
            task.wait(10)
        end
    end
}

local SectionTPs = TabMisc:Section{
    Name = "Keybind Teleport"
}

SectionTPs:Keybind{
    Name = "Spawn",
    Keybind = Enum.KeyCode.One,
    Callback = function()
        Library.WorldCmds.Load("Spawn")
    end
}

SectionTPs:Keybind{
    Name = "Fantasy",
    Keybind = Enum.KeyCode.Two,
    Callback = function()
        Library.WorldCmds.Load("Fantasy")
    end
}

SectionTPs:Keybind{
    Name = "Tech",
    Keybind = Enum.KeyCode.Three,
    Callback = function()
        Library.WorldCmds.Load("Tech")
    end
}

SectionTPs:Keybind{
    Name = "Axolotl Ocean",
    Keybind = Enum.KeyCode.Four,
    Callback = function()
        Library.WorldCmds.Load("Axolotl Ocean")
    end
}

SectionTPs:Keybind{
    Name = "Pixel",
    Keybind = Enum.KeyCode.Five,
    Callback = function()
        Library.WorldCmds.Load("Pixel")
    end
}
