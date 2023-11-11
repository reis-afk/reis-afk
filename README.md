getgenv().kill = true; -- set to false then execute to stop

while getgenv().kill == true and task.wait() do
    for i,v in pairs(game.Players:GetChildren()) do
        if v ~= game.Players.LocalPlayer and v.Character ~= nil then
        pcall(function()
local args = {
    [1] = v.Character.Humanoid,
    [2] = v.Character.Head,
    [3] = Vector3.new(0, 0, 0)
}

game:GetService("Players").LocalPlayer.Character.Pistola.EventsFolder.InflictTarget:FireServer(unpack(args))
        end)
        end
    end
end
