local function aimAtPlayer(player)
    if player.Character and player.Character:FindFirstChild("Head") then
        local headPosition = player.Character.Head.Position
        local camera = game.Workspace.CurrentCamera
        camera.CFrame = CFrame.new(camera.CFrame.Position, headPosition)
    end
end

while true do
    for _, player in pairs(game.Players:GetPlayers()) do
        if player ~= game.Players.LocalPlayer and player.Character then
            aimAtPlayer(player)
            wait(0.1)
        end
    end
    wait(0.1)
end
