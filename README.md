-- LocalScript para automatizar o processo no Ata

local Players = game:GetService("Players")
local player = Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local teleportService = game:GetService("TeleportService")

-- Função para teletransportar o jogador
local function teleportToDungeon()
    local dungeonPosition = Vector3.new(0, 200, 0) -- Altere as coordenadas para a posição da dungeon
    character:SetPrimaryPartCFrame(CFrame.new(dungeonPosition))
end

-- Função para pegar a missão
local function acceptQuest()
    -- Aqui você deve adicionar o código específico para aceitar a missão
    -- Isso depende de como a missão é estruturada no Ata
    print("Missão aceita!")
end

-- Função para teletransportar ao boss
local function teleportToBoss()
    local bossPosition = Vector3.new(0, 300, 0) -- Altere as coordenadas para a posição do boss
    character:SetPrimaryPartCFrame(CFrame.new(bossPosition))
end

-- Função para matar o boss
local function defeatBoss()
    -- Aqui você deve adicionar o código específico para atacar o boss
    -- Isso pode variar de acordo com as mecânicas do Ata
    print("Boss derrotado!")
end

-- Função principal que executa o ciclo
local function main()
    while true do
        teleportToDungeon()
        wait(2) -- Espera um pouco para garantir que o teletransporte foi concluído
        
        acceptQuest()
        wait(2) -- Espera um pouco para garantir que a missão foi aceita
        
        teleportToBoss()
        wait(2) -- Espera um pouco para garantir que o teletransporte foi concluído
        
        defeatBoss()
        wait(5) -- Espera um pouco antes de repetir todo o processo
    end
end

-- Inicia o processo
main()
