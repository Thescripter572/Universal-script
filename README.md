# Universal-script
 a universal jjs and tsb script 
-- LocalScript (put in StarterPlayerScripts or StarterGui)

local player = game.Players.LocalPlayer
local gui = Instance.new("ScreenGui")
gui.Parent = player:WaitForChild("PlayerGui")

-- Main black box
local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 400, 0, 250)
frame.Position = UDim2.new(0.5, -200, 0.5, -125)
frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
frame.Parent = gui

-- Text instructions
local text = Instance.new("TextLabel")
text.Size = UDim2.new(1, -20, 0, 150)
text.Position = UDim2.new(0, 10, 0, 10)
text.BackgroundTransparency = 1
text.TextColor3 = Color3.fromRGB(255, 255, 255)
text.TextXAlignment = Enum.TextXAlignment.Left
text.TextYAlignment = Enum.TextYAlignment.Top
text.TextWrapped = true
text.Font = Enum.Font.SourceSansBold
text.TextSize = 18
text.Text = [[
How to get script

Step 1: Click the Box
Step 2: Paste it into your web browser
Step 3: Join group
Step 4: Rejoin and Enjoy!!
]]
text.Parent = frame

-- Blue copy button
local button = Instance.new("TextButton")
button.Size = UDim2.new(1, -20, 0, 40)
button.Position = UDim2.new(0, 10, 1, -50)
button.BackgroundColor3 = Color3.fromRGB(0, 120, 255)
button.TextColor3 = Color3.fromRGB(255, 255, 255)
button.Font = Enum.Font.SourceSansBold
button.TextSize = 18
button.Text = "Click to Copy"
button.Parent = frame

local copyText = "https://linkurl.pk/TF-pGmhY"

button.MouseButton1Click:Connect(function()
    if setclipboard then
        setclipboard(copyText)
        button.Text = "Copied!"
        wait(1)
        button.Text = "Click to Copy"
    else
        button.Text = "Clipboard not supported"
    end
end)
