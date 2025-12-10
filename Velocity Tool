local Players = game:GetService("Players")
local player = Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")

-- Criar a tool
local tool = Instance.new("Tool")
tool.Name = "Velocity Tool"
tool.RequiresHandle = false -- Não precisa de handle
tool.Parent = backpack

local function giveSpeed()
	local character = player.Character or player.CharacterAdded:Wait()
	local humanoid = character:WaitForChild("Humanoid")

	humanoid.WalkSpeed = 200
end

local function removeSpeed()
	local character = player.Character or player.CharacterAdded:Wait()
	local humanoid = character:WaitForChild("Humanoid")

	humanoid.WalkSpeed = 16
end

-- Quando equipar a tool
tool.Equipped:Connect(giveSpeed)

-- Quando desequipar
tool.Unequipped:Connect(removeSpeed)

-- Se o player morrer equipado, reseta o speed
player.CharacterAdded:Connect(function(char)
	char:WaitForChild("Humanoid").WalkSpeed = 16
end)

