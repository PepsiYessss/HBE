-- Jogador base
local player = {
    name = "Jogador1",
    hasBall = false,
    baseHitbox = { width = 1, height = 2 }, -- tamanho base do jogador
    hitbox = { width = 1, height = 2 } -- o hitbox atual
}

-- Atualiza a hitbox com base na posse de bola
function updateHitbox(player)
    if player.hasBall then
        -- Hitbox reduzida para melhorar controle e evitar colisão injusta
        player.hitbox.width = player.baseHitbox.width * 0.8
        player.hitbox.height = player.baseHitbox.height * 0.8
    else
        -- Hitbox expandida para jogadas normais (1.5x)
        player.hitbox.width = player.baseHitbox.width * 1.5
        player.hitbox.height = player.baseHitbox.height * 1.5
    end
end

-- Simula troca de posse de bola
function setBallPossession(player, hasBall)
    player.hasBall = hasBall
    updateHitbox(player)
end

-- Testando
setBallPossession(player, false)
print("Sem bola - Hitbox:", player.hitbox.width, player.hitbox.height)

setBallPossession(player, true)
print("Com bola - Hitbox:", player.hitbox.width, player.hitbox.height)
