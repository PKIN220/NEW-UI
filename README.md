local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:FindFirstChildOfClass("Humanoid")

local speedMultiplier = 50

local userInput = game:GetService("UserInputService")

userInput.InputBegan:Connect(function(input, gameProcessed)
    if not gameProcessed then
        if input.KeyCode == Enum.KeyCode.LeftShift then
            humanoid.WalkSpeed = 16 * speedMultiplier
        end
    end
end)

userInput.InputEnded:Connect(function(input, gameProcessed)
    if input.KeyCode == Enum.KeyCode.LeftShift then
        humanoid.WalkSpeed = 16
    end
end)
