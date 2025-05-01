function validateHitbox(player)
    local w, h = player.hitbox.width, player.hitbox.height
    local bw, bh = player.baseHitbox.width, player.baseHitbox.height

    if player.hasBall and (w ~= bw / 3 or h ~= bh / 3) then
        print("[ALERTA] Hitbox incorreta com bola!")
    elseif not player.hasBall and (w ~= bw * 3 or h ~= bh * 3) then
        print("[ALERTA] Hitbox incorreta sem bola!")
    else
        print("Hitbox de " .. player.name .. " está correta.")
    end
end
