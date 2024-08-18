speedButton.MouseButton1Click:Connect(function()
    speedEnabled = not speedEnabled
    adjustSpeed()
end)

-- Fly Toggle
local flyEnabled = false
local flySpeed = 50
local bodyVelocity = Instance.new("BodyVelocity")
bodyVelocity.Velocity = Vector3.new(0, 0, 0)
bodyVelocity.MaxForce = Vector3.new()

local function toggleFly()
    flyEnabled = not flyEnabled
    if flyEnabled then
        bodyVelocity.Parent = player.Character.HumanoidRootPart
        RunService.RenderStepped:Connect(function()
            if flyEnabled then
                bodyVelocity.Velocity = Camera.CFrame.LookVector * flySpeed
            end
        end)
    else
        bodyVelocity.Parent = nil
    end
end

flyButton.MouseButton1Click:Connect(function()
    toggleFly()
end)

-- Anti-Cheat Bypass Toggle
local antiCheatEnabled = false

local function toggleAntiCheat()
    antiCheatEnabled = not antiCheatEnabled
    if antiCheatEnabled then
        -- Add code here to bypass anti-cheat mechanisms
        -- Note: Be cautious as this can violate game rules and may lead to a ban
    else
        -- Restore or reset any changes made for anti-cheat bypass
    end
end

antiCheatButton.MouseButton1Click:Connect(function()
    toggleAntiCheat()
end)
