local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "PedrinHub | Created By Pedrin031",
   Icon = 0, -- Sem ícone por enquanto
   LoadingTitle = "PedrinHub Loading...",
   LoadingSubtitle = "Created by Pedrin031",
   Theme = "Bloom",
   
   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false,

   ConfigurationSaving = {
      Enabled = true,
      FolderName = "PedrinHub",
      FileName = "PedrinHub_Config"
   },

   Discord = {
      Enabled = true,
      Invite = "jfKVrrMx",
      RememberJoins = true
   },

   KeySystem = false, -- Sem sistema de key para facilitar o acesso
})

local HomeTab = Window:CreateTab("🏠 Home", 4483362458)
local ScriptsTab = Window:CreateTab("📜 Scripts", nil)
local UniversalTab = Window:CreateTab("🚀 Universal", nil)

local HomeSection = HomeTab:CreateSection("Bem-vindo ao PedrinHub!")
local ScriptsSection = ScriptsTab:CreateSection("Scripts Disponíveis")
local UniversalSection = UniversalTab:CreateSection("Funções Universais")

-- Botões de Scripts
ScriptsTab:CreateButton({
    Name = "Fight In A School | OP Script",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/fight-in-a-school-yn-Hub-Script-28121"))()
    end,
})

ScriptsTab:CreateButton({
    Name = "Infinite Yield | Admin Commands",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
    end,
})

ScriptsTab:CreateButton({
    Name = "LUCKY BLOCK Battlegrounds",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/idkevenknowburh/c/refs/heads/main/d'))()
    end,
})

ScriptsTab:CreateButton({
    Name = "Legends of Speed V2 | OP",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/idkevenknowburh/legends-of-speed/refs/heads/main/script'))()
    end,
})

ScriptsTab:CreateButton({
    Name = "Murder Mystery 2 | Admin Panel",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/MarsQQ/ScriptHubScripts/master/MM2%20Admin%20Panel'))()
    end,
})

ScriptsTab:CreateButton({
    Name = "Prison Life | OP Script",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/devguy100/PrizzLife/main/Source/release_v0.8.1.lua'))()
    end,
})

ScriptsTab:CreateButton({
    Name = "Fisch | Speed Hub",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/AhmadV99/Speed-Hub-X/main/Speed%20Hub%20X.lua"))()
    end,
})

ScriptsTab:CreateButton({
    Name = "KAT! | OP Script",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/idkevenknowburh/kat/refs/heads/main/s'))()
    end,
})

UniversalTab:CreateToggle({
    Name = "OP AutoClicker",
    CurrentValue = false,
    Flag = "AutoClicker",
    Callback = function(Value)
        if Value then
            loadstring(game:HttpGet("https://raw.githubusercontent.com/Hosvile/The-telligence/main/MC%20KSystem%202"))()
        end
    end,
})

UniversalTab:CreateSlider({
    Name = "WalkSpeed Changer",
    Range = {0, 200},
    Increment = 10,
    Suffix = "Speed",
    CurrentValue = 16,
    Flag = "WalkSpeedChanger",
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
    end,
})

UniversalTab:CreateSlider({
    Name = "JumpPower Changer",
    Range = {0, 300},
    Increment = 10,
    Suffix = "JumpPower",
    CurrentValue = 50,
    Flag = "JumpPowerChanger",
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.JumpPower = Value
    end,
})

UniversalTab:CreateButton({
    Name = "Infinite Jump (Ativar)",
    Callback = function()
        local UserInputService = game:GetService("UserInputService")
        local humanoid = game.Players.LocalPlayer.Character:WaitForChild("Humanoid")

        UserInputService.JumpRequest:Connect(function()
            if humanoid then
                humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
            end
        end)
    end,
})

UniversalTab:CreateButton({
    Name = "Resetar personagem (Desativar Infinite Jump)",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player.Character and player.Character:FindFirstChild("Humanoid") then
            player.Character.Humanoid.Health = 0
        end
    end,
})

UniversalTab:CreateButton({
    Name = "Fly GUI V3",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/XNEOFF/FlyGuiV3/main/FlyGuiV3.txt"))()
    end,
})

UniversalTab:CreateButton({
    Name = "(FE) Aimbot GUI (Funciona em todos os jogos)",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/XNEOFF/AimbotGUI/main/AimbotGUI.txt"))()
    end,
})

Rayfield:LoadConfiguration()
