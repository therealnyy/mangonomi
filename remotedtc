-- Remote Event Detector & Fire UI with Advanced Color Customization
-- Place this in a LocalScript inside StarterPlayer > StarterPlayerScripts

local Players = game:GetService("Players")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Create ScreenGui
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "RemoteDetectorUI"
screenGui.ResetOnSpawn = false
screenGui.Parent = playerGui

-- Main Frame
local mainFrame = Instance.new("Frame")
mainFrame.Name = "MainFrame"
mainFrame.Size = UDim2.new(0, 400, 0, 500)
mainFrame.Position = UDim2.new(0.5, -200, 0.5, -250)
mainFrame.BackgroundColor3 = Color3.fromRGB(35, 35, 40)
mainFrame.BorderSizePixel = 0
mainFrame.Active = true
mainFrame.Draggable = true
mainFrame.Parent = screenGui

local mainCorner = Instance.new("UICorner")
mainCorner.CornerRadius = UDim.new(0, 8)
mainCorner.Parent = mainFrame

-- Title Bar
local titleBar = Instance.new("Frame")
titleBar.Name = "TitleBar"
titleBar.Size = UDim2.new(1, 0, 0, 40)
titleBar.BackgroundColor3 = Color3.fromRGB(25, 25, 30)
titleBar.BorderSizePixel = 0
titleBar.Parent = mainFrame

local titleCorner = Instance.new("UICorner")
titleCorner.CornerRadius = UDim.new(0, 8)
titleCorner.Parent = titleBar

-- Title Text
local titleText = Instance.new("TextLabel")
titleText.Size = UDim2.new(1, -180, 1, 0)
titleText.BackgroundTransparency = 1
titleText.Text = "Remote Event Detector"
titleText.TextColor3 = Color3.fromRGB(255, 255, 255)
titleText.TextSize = 18
titleText.Font = Enum.Font.GothamBold
titleText.TextXAlignment = Enum.TextXAlignment.Left
titleText.Position = UDim2.new(0, 15, 0, 0)
titleText.Parent = titleBar

-- Color Settings Button
local colorButton = Instance.new("TextButton")
colorButton.Name = "ColorButton"
colorButton.Size = UDim2.new(0, 35, 0, 30)
colorButton.Position = UDim2.new(1, -170, 0.5, -15)
colorButton.BackgroundColor3 = Color3.fromRGB(150, 100, 255)
colorButton.Text = "🎨"
colorButton.TextColor3 = Color3.fromRGB(255, 255, 255)
colorButton.TextSize = 18
colorButton.Font = Enum.Font.GothamBold
colorButton.BorderSizePixel = 0
colorButton.Parent = titleBar

local colorBtnCorner = Instance.new("UICorner")
colorBtnCorner.CornerRadius = UDim.new(0, 6)
colorBtnCorner.Parent = colorButton

-- Scan Button
local scanButton = Instance.new("TextButton")
scanButton.Name = "ScanButton"
scanButton.Size = UDim2.new(0, 80, 0, 30)
scanButton.Position = UDim2.new(1, -125, 0.5, -15)
scanButton.BackgroundColor3 = Color3.fromRGB(0, 170, 255)
scanButton.Text = "Scan"
scanButton.TextColor3 = Color3.fromRGB(255, 255, 255)
scanButton.TextSize = 14
scanButton.Font = Enum.Font.GothamBold
scanButton.BorderSizePixel = 0
scanButton.Parent = titleBar

local scanCorner = Instance.new("UICorner")
scanCorner.CornerRadius = UDim.new(0, 6)
scanCorner.Parent = scanButton

-- Close Button
local closeButton = Instance.new("TextButton")
closeButton.Name = "CloseButton"
closeButton.Size = UDim2.new(0, 30, 0, 30)
closeButton.Position = UDim2.new(1, -35, 0.5, -15)
closeButton.BackgroundColor3 = Color3.fromRGB(255, 70, 70)
closeButton.Text = "X"
closeButton.TextColor3 = Color3.fromRGB(255, 255, 255)
closeButton.TextSize = 16
closeButton.Font = Enum.Font.GothamBold
closeButton.BorderSizePixel = 0
closeButton.Parent = titleBar

local closeCorner = Instance.new("UICorner")
closeCorner.CornerRadius = UDim.new(0, 6)
closeCorner.Parent = closeButton

-- Search Bar
local searchBar = Instance.new("TextBox")
searchBar.Name = "SearchBar"
searchBar.Size = UDim2.new(1, -20, 0, 35)
searchBar.Position = UDim2.new(0, 10, 0, 45)
searchBar.BackgroundColor3 = Color3.fromRGB(45, 45, 50)
searchBar.PlaceholderText = "Search remotes..."
searchBar.PlaceholderColor3 = Color3.fromRGB(120, 120, 120)
searchBar.Text = ""
searchBar.TextColor3 = Color3.fromRGB(255, 255, 255)
searchBar.TextSize = 13
searchBar.Font = Enum.Font.Gotham
searchBar.TextXAlignment = Enum.TextXAlignment.Left
searchBar.ClearTextOnFocus = false
searchBar.BorderSizePixel = 0
searchBar.Parent = mainFrame

local searchCorner = Instance.new("UICorner")
searchCorner.CornerRadius = UDim.new(0, 6)
searchCorner.Parent = searchBar

local searchPadding = Instance.new("UIPadding")
searchPadding.PaddingLeft = UDim.new(0, 10)
searchPadding.PaddingRight = UDim.new(0, 10)
searchPadding.Parent = searchBar

-- Status Label
local statusLabel = Instance.new("TextLabel")
statusLabel.Size = UDim2.new(1, -20, 0, 20)
statusLabel.Position = UDim2.new(0, 10, 0, 85)
statusLabel.BackgroundTransparency = 1
statusLabel.Text = "Click 'Scan' to detect remote events"
statusLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
statusLabel.TextSize = 11
statusLabel.Font = Enum.Font.Gotham
statusLabel.TextXAlignment = Enum.TextXAlignment.Left
statusLabel.Parent = mainFrame

-- ScrollingFrame for Remote List
local scrollFrame = Instance.new("ScrollingFrame")
scrollFrame.Name = "RemoteList"
scrollFrame.Size = UDim2.new(1, -20, 1, -120)
scrollFrame.Position = UDim2.new(0, 10, 0, 110)
scrollFrame.BackgroundColor3 = Color3.fromRGB(45, 45, 50)
scrollFrame.BorderSizePixel = 0
scrollFrame.ScrollBarThickness = 6
scrollFrame.Parent = mainFrame

local scrollCorner = Instance.new("UICorner")
scrollCorner.CornerRadius = UDim.new(0, 6)
scrollCorner.Parent = scrollFrame

local listLayout = Instance.new("UIListLayout")
listLayout.SortOrder = Enum.SortOrder.LayoutOrder
listLayout.Padding = UDim.new(0, 5)
listLayout.Parent = scrollFrame

-- COLOR CUSTOMIZATION PANEL
local colorPanel = Instance.new("Frame")
colorPanel.Name = "ColorPanel"
colorPanel.Size = UDim2.new(0, 380, 0, 520)
colorPanel.Position = UDim2.new(0.5, -190, 0.5, -260)
colorPanel.BackgroundColor3 = Color3.fromRGB(30, 30, 35)
colorPanel.BorderSizePixel = 0
colorPanel.Visible = false
colorPanel.Active = true
colorPanel.Draggable = true
colorPanel.Parent = screenGui

local colorPanelCorner = Instance.new("UICorner")
colorPanelCorner.CornerRadius = UDim.new(0, 10)
colorPanelCorner.Parent = colorPanel

-- Color Panel Title Bar
local colorTitleBar = Instance.new("Frame")
colorTitleBar.Size = UDim2.new(1, 0, 0, 40)
colorTitleBar.BackgroundColor3 = Color3.fromRGB(20, 20, 25)
colorTitleBar.BorderSizePixel = 0
colorTitleBar.Parent = colorPanel

local colorTitleCorner = Instance.new("UICorner")
colorTitleCorner.CornerRadius = UDim.new(0, 10)
colorTitleCorner.Parent = colorTitleBar

local colorTitleText = Instance.new("TextLabel")
colorTitleText.Size = UDim2.new(1, -50, 1, 0)
colorTitleText.Position = UDim2.new(0, 15, 0, 0)
colorTitleText.BackgroundTransparency = 1
colorTitleText.Text = "Color Customization"
colorTitleText.TextColor3 = Color3.fromRGB(255, 255, 255)
colorTitleText.TextSize = 16
colorTitleText.Font = Enum.Font.GothamBold
colorTitleText.TextXAlignment = Enum.TextXAlignment.Left
colorTitleText.Parent = colorTitleBar

local colorCloseBtn = Instance.new("TextButton")
colorCloseBtn.Size = UDim2.new(0, 30, 0, 30)
colorCloseBtn.Position = UDim2.new(1, -35, 0.5, -15)
colorCloseBtn.BackgroundColor3 = Color3.fromRGB(255, 70, 70)
colorCloseBtn.Text = "X"
colorCloseBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
colorCloseBtn.TextSize = 14
colorCloseBtn.Font = Enum.Font.GothamBold
colorCloseBtn.BorderSizePixel = 0
colorCloseBtn.Parent = colorTitleBar

local colorCloseBtnCorner = Instance.new("UICorner")
colorCloseBtnCorner.CornerRadius = UDim.new(0, 6)
colorCloseBtnCorner.Parent = colorCloseBtn

-- Color Panel Content
local colorContent = Instance.new("ScrollingFrame")
colorContent.Size = UDim2.new(1, -20, 1, -55)
colorContent.Position = UDim2.new(0, 10, 0, 45)
colorContent.BackgroundTransparency = 1
colorContent.BorderSizePixel = 0
colorContent.ScrollBarThickness = 4
colorContent.Parent = colorPanel

local colorContentLayout = Instance.new("UIListLayout")
colorContentLayout.SortOrder = Enum.SortOrder.LayoutOrder
colorContentLayout.Padding = UDim.new(0, 15)
colorContentLayout.Parent = colorContent

-- Current color scheme
local colorScheme = {
    mainBg = Color3.fromRGB(35, 35, 40),
    titleBar = Color3.fromRGB(25, 25, 30),
    scrollBg = Color3.fromRGB(45, 45, 50),
    entryBg = Color3.fromRGB(55, 55, 60),
    accentColor = Color3.fromRGB(0, 170, 255)
}

-- Utility functions
local function rgbToHex(color)
    return string.format("%02X%02X%02X", 
        math.floor(color.R * 255), 
        math.floor(color.G * 255), 
        math.floor(color.B * 255))
end

local function hexToRgb(hex)
    hex = hex:gsub("#", "")
    if #hex == 6 then
        local r = tonumber(hex:sub(1, 2), 16) or 0
        local g = tonumber(hex:sub(3, 4), 16) or 0
        local b = tonumber(hex:sub(5, 6), 16) or 0
        return Color3.fromRGB(r, g, b)
    end
    return Color3.fromRGB(255, 255, 255)
end

local function hsvToRgb(h, s, v)
    local r, g, b
    local i = math.floor(h * 6)
    local f = h * 6 - i
    local p = v * (1 - s)
    local q = v * (1 - f * s)
    local t = v * (1 - (1 - f) * s)
    i = i % 6
    if i == 0 then r, g, b = v, t, p
    elseif i == 1 then r, g, b = q, v, p
    elseif i == 2 then r, g, b = p, v, t
    elseif i == 3 then r, g, b = p, q, v
    elseif i == 4 then r, g, b = t, p, v
    elseif i == 5 then r, g, b = v, p, q
    end
    return Color3.fromRGB(r * 255, g * 255, b * 255)
end

-- Apply colors to UI
function applyColors()
    mainFrame.BackgroundColor3 = colorScheme.mainBg
    titleBar.BackgroundColor3 = colorScheme.titleBar
    searchBar.BackgroundColor3 = colorScheme.scrollBg
    scrollFrame.BackgroundColor3 = colorScheme.scrollBg
    scanButton.BackgroundColor3 = colorScheme.accentColor
    
    for _, entry in ipairs(scrollFrame:GetChildren()) do
        if entry:IsA("Frame") and entry.Name:match("Entry_") then
            entry.BackgroundColor3 = colorScheme.entryBg
        end
    end
end

-- Function to create advanced color picker
local function createColorPicker(name, displayName, colorKey)
    local section = Instance.new("Frame")
    section.Name = name
    section.Size = UDim2.new(1, 0, 0, 320)
    section.BackgroundColor3 = Color3.fromRGB(40, 40, 45)
    section.BorderSizePixel = 0
    section.Parent = colorContent
    
    local sectionCorner = Instance.new("UICorner")
    sectionCorner.CornerRadius = UDim.new(0, 8)
    sectionCorner.Parent = section
    
    -- Section Label
    local label = Instance.new("TextLabel")
    label.Size = UDim2.new(1, -20, 0, 25)
    label.Position = UDim2.new(0, 10, 0, 5)
    label.BackgroundTransparency = 1
    label.Text = displayName
    label.TextColor3 = Color3.fromRGB(255, 255, 255)
    label.TextSize = 14
    label.Font = Enum.Font.GothamBold
    label.TextXAlignment = Enum.TextXAlignment.Left
    label.Parent = section
    
    local currentColor = colorScheme[colorKey]
    local currentH, currentS, currentV = 0, 1, 1
    
    -- 2D Gradient Picker (Saturation/Value)
    local gradientPicker = Instance.new("ImageButton")
    gradientPicker.Size = UDim2.new(1, -100, 0, 180)
    gradientPicker.Position = UDim2.new(0, 10, 0, 35)
    gradientPicker.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
    gradientPicker.BorderSizePixel = 0
    gradientPicker.Parent = section
    
    local gradientCorner = Instance.new("UICorner")
    gradientCorner.CornerRadius = UDim.new(0, 6)
    gradientCorner.Parent = gradientPicker
    
    -- White to transparent gradient (saturation)
    local satGradient = Instance.new("UIGradient")
    satGradient.Color = ColorSequence.new(Color3.fromRGB(255, 255, 255), Color3.fromRGB(255, 255, 255))
    satGradient.Transparency = NumberSequence.new({
        NumberSequenceKeypoint.new(0, 0),
        NumberSequenceKeypoint.new(1, 1)
    })
    satGradient.Parent = gradientPicker
    
    -- Black overlay for value
    local valueOverlay = Instance.new("Frame")
    valueOverlay.Size = UDim2.new(1, 0, 1, 0)
    valueOverlay.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    valueOverlay.BorderSizePixel = 0
    valueOverlay.Parent = gradientPicker
    
    local valueGradient = Instance.new("UIGradient")
    valueGradient.Rotation = 90
    valueGradient.Transparency = NumberSequence.new({
        NumberSequenceKeypoint.new(0, 1),
        NumberSequenceKeypoint.new(1, 0)
    })
    valueGradient.Parent = valueOverlay
    
    -- Picker cursor
    local cursor = Instance.new("Frame")
    cursor.Size = UDim2.new(0, 12, 0, 12)
    cursor.Position = UDim2.new(currentS, -6, 1 - currentV, -6)
    cursor.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    cursor.BorderSizePixel = 2
    cursor.BorderColor3 = Color3.fromRGB(0, 0, 0)
    cursor.Parent = gradientPicker
    
    local cursorCorner = Instance.new("UICorner")
    cursorCorner.CornerRadius = UDim.new(1, 0)
    cursorCorner.Parent = cursor
    
    -- Hue Slider (vertical rainbow)
    local hueSlider = Instance.new("ImageButton")
    hueSlider.Size = UDim2.new(0, 30, 0, 180)
    hueSlider.Position = UDim2.new(1, -80, 0, 35)
    hueSlider.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    hueSlider.BorderSizePixel = 0
    hueSlider.Parent = section
    
    local hueCorner = Instance.new("UICorner")
    hueCorner.CornerRadius = UDim.new(0, 6)
    hueCorner.Parent = hueSlider
    
    local hueGradient = Instance.new("UIGradient")
    hueGradient.Rotation = 90
    hueGradient.Color = ColorSequence.new({
        ColorSequenceKeypoint.new(0, Color3.fromRGB(255, 0, 0)),
        ColorSequenceKeypoint.new(0.17, Color3.fromRGB(255, 255, 0)),
        ColorSequenceKeypoint.new(0.33, Color3.fromRGB(0, 255, 0)),
        ColorSequenceKeypoint.new(0.5, Color3.fromRGB(0, 255, 255)),
        ColorSequenceKeypoint.new(0.67, Color3.fromRGB(0, 0, 255)),
        ColorSequenceKeypoint.new(0.83, Color3.fromRGB(255, 0, 255)),
        ColorSequenceKeypoint.new(1, Color3.fromRGB(255, 0, 0))
    })
    hueGradient.Parent = hueSlider
    
    -- Hue cursor
    local hueCursor = Instance.new("Frame")
    hueCursor.Size = UDim2.new(1, 4, 0, 4)
    hueCursor.Position = UDim2.new(0, -2, 0, -2)
    hueCursor.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    hueCursor.BorderSizePixel = 2
    hueCursor.BorderColor3 = Color3.fromRGB(0, 0, 0)
    hueCursor.Parent = hueSlider
    
    local hueCursorCorner = Instance.new("UICorner")
    hueCursorCorner.CornerRadius = UDim.new(1, 0)
    hueCursorCorner.Parent = hueCursor
    
    -- Color Preview
    local preview = Instance.new("Frame")
    preview.Size = UDim2.new(0, 60, 0, 40)
    preview.Position = UDim2.new(1, -70, 0, 220)
    preview.BackgroundColor3 = currentColor
    preview.BorderSizePixel = 0
    preview.Parent = section
    
    local previewCorner = Instance.new("UICorner")
    previewCorner.CornerRadius = UDim.new(0, 6)
    previewCorner.Parent = preview
    
    -- Hex Input
    local hexLabel = Instance.new("TextLabel")
    hexLabel.Size = UDim2.new(0, 40, 0, 30)
    hexLabel.Position = UDim2.new(0, 10, 0, 225)
    hexLabel.BackgroundTransparency = 1
    hexLabel.Text = "Hex:"
    hexLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
    hexLabel.TextSize = 12
    hexLabel.Font = Enum.Font.GothamBold
    hexLabel.TextXAlignment = Enum.TextXAlignment.Left
    hexLabel.Parent = section
    
    local hexInput = Instance.new("TextBox")
    hexInput.Size = UDim2.new(0, 100, 0, 30)
    hexInput.Position = UDim2.new(0, 50, 0, 225)
    hexInput.BackgroundColor3 = Color3.fromRGB(50, 50, 55)
    hexInput.Text = rgbToHex(currentColor)
    hexInput.TextColor3 = Color3.fromRGB(255, 255, 255)
    hexInput.TextSize = 11
    hexInput.Font = Enum.Font.Gotham
    hexInput.BorderSizePixel = 0
    hexInput.Parent = section
    
    local hexCorner = Instance.new("UICorner")
    hexCorner.CornerRadius = UDim.new(0, 4)
    hexCorner.Parent = hexInput
    
    -- RGB Labels
    local rgbLabel = Instance.new("TextLabel")
    rgbLabel.Size = UDim2.new(0, 200, 0, 25)
    rgbLabel.Position = UDim2.new(0, 10, 0, 265)
    rgbLabel.BackgroundTransparency = 1
    rgbLabel.Text = string.format("RGB: %d, %d, %d", 
        math.floor(currentColor.R * 255),
        math.floor(currentColor.G * 255),
        math.floor(currentColor.B * 255))
    rgbLabel.TextColor3 = Color3.fromRGB(180, 180, 180)
    rgbLabel.TextSize = 11
    rgbLabel.Font = Enum.Font.Gotham
    rgbLabel.TextXAlignment = Enum.TextXAlignment.Left
    rgbLabel.Parent = section
    
    -- Update function
    local function updateColor()
        local newColor = hsvToRgb(currentH, currentS, currentV)
        preview.BackgroundColor3 = newColor
        hexInput.Text = rgbToHex(newColor)
        rgbLabel.Text = string.format("RGB: %d, %d, %d", 
            math.floor(newColor.R * 255),
            math.floor(newColor.G * 255),
            math.floor(newColor.B * 255))
        colorScheme[colorKey] = newColor
        applyColors()
    end
    
    -- Gradient picker interaction
    local gradientDragging = false
    
    gradientPicker.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 then
            gradientDragging = true
        end
    end)
    
    gradientPicker.InputEnded:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 then
            gradientDragging = false
        end
    end)
    
    gradientPicker.InputChanged:Connect(function(input)
        if gradientDragging and input.UserInputType == Enum.UserInputType.MouseMovement then
            local posX = (input.Position.X - gradientPicker.AbsolutePosition.X) / gradientPicker.AbsoluteSize.X
            local posY = (input.Position.Y - gradientPicker.AbsolutePosition.Y) / gradientPicker.AbsoluteSize.Y
            currentS = math.clamp(posX, 0, 1)
            currentV = math.clamp(1 - posY, 0, 1)
            cursor.Position = UDim2.new(currentS, -6, 1 - currentV, -6)
            updateColor()
        end
    end)
    
    -- Hue slider interaction
    local hueDragging = false
    
    hueSlider.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 then
            hueDragging = true
        end
    end)
    
    hueSlider.InputEnded:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 then
            hueDragging = false
        end
    end)
    
    hueSlider.InputChanged:Connect(function(input)
        if hueDragging and input.UserInputType == Enum.UserInputType.MouseMovement then
            local posY = (input.Position.Y - hueSlider.AbsolutePosition.Y) / hueSlider.AbsoluteSize.Y
            currentH = math.clamp(posY, 0, 1)
            hueCursor.Position = UDim2.new(0, -2, currentH, -2)
            local hueColor = hsvToRgb(currentH, 1, 1)
            gradientPicker.BackgroundColor3 = hueColor
            updateColor()
        end
    end)
    
    -- Hex input handler
    hexInput.FocusLost:Connect(function()
        local newColor = hexToRgb(hexInput.Text)
        colorScheme[colorKey] = newColor
        preview.BackgroundColor3 = newColor
        applyColors()
    end)
    
    return section
end

-- Create color pickers
createColorPicker("MainBgPicker", "Main Background", "mainBg")
createColorPicker("TitleBarPicker", "Title Bar", "titleBar")
createColorPicker("ScrollBgPicker", "Search/Scroll Background", "scrollBg")
createColorPicker("EntryBgPicker", "Entry Background", "entryBg")
createColorPicker("AccentPicker", "Accent Color", "accentColor")

colorContent.CanvasSize = UDim2.new(0, 0, 0, colorContentLayout.AbsoluteContentSize.Y + 10)

-- Store all remotes
local allRemotes = {}

-- Function to create a remote entry
local function createRemoteEntry(remote, index)
    local entry = Instance.new("Frame")
    entry.Name = "Entry_" .. index
    entry.Size = UDim2.new(1, -10, 0, 50)
    entry.BackgroundColor3 = colorScheme.entryBg
    entry.BorderSizePixel = 0
    entry.Parent = scrollFrame
    
    local entryCorner = Instance.new("UICorner")
    entryCorner.CornerRadius = UDim.new(0, 4)
    entryCorner.Parent = entry
    
    local nameLabel = Instance.new("TextLabel")
    nameLabel.Size = UDim2.new(1, -90, 0.5, 0)
    nameLabel.Position = UDim2.new(0, 10, 0, 0)
    nameLabel.BackgroundTransparency = 1
    nameLabel.Text = remote.Name
    nameLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
    nameLabel.TextSize = 13
    nameLabel.Font = Enum.Font.GothamBold
    nameLabel.TextXAlignment = Enum.TextXAlignment.Left
    nameLabel.TextTruncate = Enum.TextTruncate.AtEnd
    nameLabel.Parent = entry
    
    local pathLabel = Instance.new("TextLabel")
    pathLabel.Size = UDim2.new(1, -90, 0.5, 0)
    pathLabel.Position = UDim2.new(0, 10, 0.5, 0)
    pathLabel.BackgroundTransparency = 1
    pathLabel.Text = remote:GetFullName()
    pathLabel.TextColor3 = Color3.fromRGB(150, 150, 150)
    pathLabel.TextSize = 10
    pathLabel.Font = Enum.Font.Gotham
    pathLabel.TextXAlignment = Enum.TextXAlignment.Left
    pathLabel.TextTruncate = Enum.TextTruncate.AtEnd
    pathLabel.Parent = entry
    
    local fireButton = Instance.new("TextButton")
    fireButton.Size = UDim2.new(0, 70, 0, 35)
    fireButton.Position = UDim2.new(1, -75, 0.5, -17.5)
    fireButton.BackgroundColor3 = Color3.fromRGB(255, 85, 85)
    fireButton.Text = "Fire"
    fireButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    fireButton.TextSize = 12
    fireButton.Font = Enum.Font.GothamBold
    fireButton.BorderSizePixel = 0
    fireButton.Parent = entry
    
    local fireCorner = Instance.new("UICorner")
    fireCorner.CornerRadius = UDim.new(0, 4)
    fireCorner.Parent = fireButton
    
    fireButton.MouseButton1Click:Connect(function()
        local success, err = pcall(function()
            remote:FireServer()
        end)
        
        if success then
            fireButton.Text = "Fired!"
            fireButton.BackgroundColor3 = Color3.fromRGB(85, 255, 85)
            task.wait(0.5)
            fireButton.Text = "Fire"
            fireButton.BackgroundColor3 = Color3.fromRGB(255, 85, 85)
        else
            fireButton.Text = "Error"
            fireButton.BackgroundColor3 = Color3.fromRGB(200, 50, 50)
            warn("Failed to fire remote:", err)
            task.wait(0.5)
            fireButton.Text = "Fire"
            fireButton.BackgroundColor3 = Color3.fromRGB(255, 85, 85)
        end
    end)
    
    return entry
end

-- Function to filter and display remotes
local function filterRemotes(searchText)
    for _, child in ipairs(scrollFrame:GetChildren()) do
        if child:IsA("Frame") then
            child:Destroy()
        end
    end
    
    local displayCount = 0
    searchText = searchText:lower()
    
    for i, remote in ipairs(allRemotes) do
        local remoteName = remote.Name:lower()
        local remotePath = remote:GetFullName():lower()
        
        if searchText == "" or remoteName:find(searchText) or remotePath:find(searchText) then
            createRemoteEntry(remote, i)
            displayCount = displayCount + 1
        end
    end
    
    if searchText == "" then
        statusLabel.Text = "Showing " .. displayCount .. " RemoteEvent(s)"
    else
        statusLabel.Text = "Found " .. displayCount .. " match(es) for '" .. searchText .. "'"
    end
    
    scrollFrame.CanvasSize = UDim2.new(0, 0, 0, listLayout.AbsoluteContentSize.Y + 10)
end

-- Function to scan for all RemoteEvents
local function scanForRemotes()
    allRemotes = {}
    
    local function searchDescendants(parent)
        for _, descendant in ipairs(parent:GetDescendants()) do
            if descendant:IsA("RemoteEvent") then
                table.insert(allRemotes, descendant)
            end
        end
    end
    
    statusLabel.Text = "Scanning..."
    task.wait(0.1)
    
    searchDescendants(game:GetService("ReplicatedStorage"))
    searchDescendants(game:GetService("Workspace"))
    searchDescendants(game:GetService("Players"))
    searchDescendants(game:GetService("Lighting"))
    searchDescendants(game:GetService("ServerScriptService"))
    searchDescendants(game:GetService("StarterPack"))
    searchDescendants(game:GetService("StarterGui"))
    
    filterRemotes(searchBar.Text)
end

-- Button handlers
closeButton.MouseButton1Click:Connect(function()
    mainFrame.Visible = false
end)

scanButton.MouseButton1Click:Connect(function()
    scanForRemotes()
end)

colorButton.MouseButton1Click:Connect(function()
    colorPanel.Visible = not colorPanel.Visible
end)

colorCloseBtn.MouseButton1Click:Connect(function()
    colorPanel.Visible = false
end)

searchBar:GetPropertyChangedSignal("Text"):Connect(function()
    filterRemotes(searchBar.Text)
end)

-- Toggle UI with keybind
local UserInputService = game:GetService("UserInputService")
UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if gameProcessed then return end
    
    if input.KeyCode == Enum.KeyCode.RightShift then
        mainFrame.Visible = not mainFrame.Visible
    end
end)

-- Auto-scan on load
task.wait(1)
scanForRemotes()

print("Remote Event Detector UI loaded! Press Right Shift to toggle UI")
