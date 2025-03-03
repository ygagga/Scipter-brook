local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Project Tubers", "DarkTheme")

local Tab = Window:NewTab("Principal")
local Section = Tab:NewSection("Funções Exploit")

local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

-- 🔥 Lagar o Servidor  
Section:NewButton("Lagar o Servidor", "Cria um alto uso de memória", function()
    while true do
        local Part = Instance.new("Part")
        Part.Parent = workspace
    end
end)

-- ⚡ Dar Velocidade a um Jogador  
Section:NewButton("Modo Turbo", "Aumenta a velocidade do seu personagem", function()
    LocalPlayer.Character.Humanoid.WalkSpeed = 100
end)

-- 🔊 Tocar Sons Específicos (Exemplo: som assustador)  
Section:NewButton("Tocar Som Assustador", "Reproduz um áudio", function()
    local Sound = Instance.new("Sound", workspace)
    Sound.SoundId = "rbxassetid://YOUR_SOUND_ID" -- Substituir pelo ID do som
    Sound.Volume = 10
    Sound:Play()
end)

-- 🚗 Matar Jogador com Carro/Sofá  
Section:NewButton("Atropelar Todos", "Mata os jogadores com um veículo", function()
    for _, player in pairs(Players:GetPlayers()) do
        if player ~= LocalPlayer and player.Character then
            local car = LocalPlayer.Character:FindFirstChild("Vehicle")
            if car then
                player.Character.Humanoid.Health = 0
            end
        end
    end
end)

-- 🏠 Trazer Jogador para sua Casa  
Section:NewButton("Teleportar Jogador para Casa", "Força um jogador a ir para sua casa", function()
    for _, player in pairs(Players:GetPlayers()) do
        if player ~= LocalPlayer and player.Character then
            player.Character:SetPrimaryPartCFrame(LocalPlayer.Character:GetPrimaryPartCFrame())
        end
    end
end)

-- 🚫 Ban Automático  
Section:NewButton("Banir Todos", "Remove jogadores do servidor", function()
    for _, player in pairs(Players:GetPlayers()) do
        if player ~= LocalPlayer then
            player:Kick("Você foi banido pelo Project Tubers!")
        end
    end
end)
