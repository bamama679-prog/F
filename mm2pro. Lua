-- MM2 PRO v2.0 - Professional Premium Script
-- Developed by goodlooking
-- Premium Quality Interface

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local TweenService = game:GetService("TweenService")
local UserInputService = game:GetService("UserInputService")
local CoreGui = game:GetService("CoreGui")
local LocalPlayer = Players.LocalPlayer
local VirtualInputManager = game:GetService("VirtualInputManager")

-- Wait for character
if not LocalPlayer.Character then
    LocalPlayer.CharacterAdded:Wait()
end
task.wait(1)

-- Professional Color Scheme
local Colors = {
    MainBg = Color3.fromRGB(15, 15, 20),
    SecondaryBg = Color3.fromRGB(22, 22, 30),
    Accent = Color3.fromRGB(255, 45, 85),
    AccentLight = Color3.fromRGB(255, 80, 110),
    TextWhite = Color3.fromRGB(255, 255, 255),
    TextGray = Color3.fromRGB(140, 140, 155),
    Border = Color3.fromRGB(40, 40, 55),
    Green = Color3.fromRGB(50, 205, 50),
    Blue = Color3.fromRGB(30, 144, 255),
    Gold = Color3.fromRGB(255, 200, 50),
    TabActive = Color3.fromRGB(255, 45, 85),
    TabInactive = Color3.fromRGB(30, 30, 40),
    ToggleOn = Color3.fromRGB(50, 205, 50),
    ToggleOff = Color3.fromRGB(50, 50, 65),
    Shadow = Color3.fromRGB(0, 0, 0)
}

-- Professional Fonts
local Fonts = {
    Title = Enum.Font.GothamBlack,
    Header = Enum.Font.GothamBold,
    Body = Enum.Font.Gotham,
    Mono = Enum.Font.GothamBold
}

-- Sound Effects
local Sounds = {
    Hover = "rbxassetid://4605925705", -- Optional hover sound
    Click = "rbxassetid://4605925705"  -- Optional click sound
}

-- ============================================
-- PROFESSIONAL GUI CREATION
-- ============================================

-- Main ScreenGui
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "MM2_Pro_" .. tostring(math.random(10000, 99999))
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.DisplayOrder = 999
ScreenGui.ResetOnSpawn = false
ScreenGui.Parent = CoreGui

-- Protect GUI if available
pcall(function()
    if syn and syn.protect_gui then
        syn.protect_gui(ScreenGui)
    elseif gethui then
        ScreenGui.Parent = gethui()
    end
end)

-- ============================================
-- LOADING ANIMATION
-- ============================================

local LoadingFrame = Instance.new("Frame")
LoadingFrame.Size = UDim2.new(1, 0, 1, 0)
LoadingFrame.BackgroundColor3 = Colors.MainBg
LoadingFrame.BorderSizePixel = 0
LoadingFrame.ZIndex = 1000
LoadingFrame.Parent = ScreenGui

local LoadingLogo = Instance.new("TextLabel")
LoadingLogo.Size = UDim2.new(0, 200, 0, 50)
LoadingLogo.Position = UDim2.new(0.5, -100, 0.4, -25)
LoadingLogo.BackgroundTransparency = 1
LoadingLogo.Text = "MM2 PRO"
LoadingLogo.TextColor3 = Colors.Accent
LoadingLogo.Font = Fonts.Title
LoadingLogo.TextSize = 36
LoadingLogo.ZIndex = 1001
LoadingLogo.Parent = LoadingFrame

local LoadingSubtitle = Instance.new("TextLabel")
LoadingSubtitle.Size = UDim2.new(0, 200, 0, 20)
LoadingSubtitle.Position = UDim2.new(0.5, -100, 0.5, 0)
LoadingSubtitle.BackgroundTransparency = 1
LoadingSubtitle.Text = "Loading premium modules..."
LoadingSubtitle.TextColor3 = Colors.TextGray
LoadingSubtitle.Font = Fonts.Body
LoadingSubtitle.TextSize = 12
LoadingSubtitle.ZIndex = 1001
LoadingSubtitle.Parent = LoadingFrame

local LoadingBar = Instance.new("Frame")
LoadingBar.Size = UDim2.new(0, 250, 0, 3)
LoadingBar.Position = UDim2.new(0.5, -125, 0.55, 0)
LoadingBar.BackgroundColor3 = Colors.Border
LoadingBar.BorderSizePixel = 0
LoadingBar.ZIndex = 1001
LoadingBar.Parent = LoadingFrame

local LoadingCorner1 = Instance.new("UICorner")
LoadingCorner1.CornerRadius = UDim.new(1, 0)
LoadingCorner1.Parent = LoadingBar

local LoadingFill = Instance.new("Frame")
LoadingFill.Size = UDim2.new(0, 0, 1, 0)
LoadingFill.BackgroundColor3 = Colors.Accent
LoadingFill.BorderSizePixel = 0
LoadingFill.ZIndex = 1002
LoadingFill.Parent = LoadingBar

local LoadingFillCorner = Instance.new("UICorner")
LoadingFillCorner.CornerRadius = UDim.new(1, 0)
LoadingFillCorner.Parent = LoadingFill

-- Loading Animation
spawn(function()
    for i = 1, 100 do
        LoadingFill:TweenSize(UDim2.new(i/100, 0, 1, 0), "Out", "Quad", 0.02, true)
        task.wait(0.02)
    end
    task.wait(0.3)
    LoadingFrame:TweenSize(UDim2.new(1, 0, 0, 0), "In", "Quad", 0.5, true)
    task.wait(0.5)
    LoadingFrame:Destroy()
end)

task.wait(2)

-- ============================================
-- MAIN CONTAINER WITH SHADOWS & EFFECTS
-- ============================================

local MainContainer = Instance.new("Frame")
MainContainer.Name = "MainContainer"
MainContainer.Size = UDim2.new(0, 620, 0, 420)
MainContainer.Position = UDim2.new(0.5, -310, 0.5, -210)
MainContainer.BackgroundColor3 = Colors.MainBg
MainContainer.BorderSizePixel = 0
MainContainer.ClipsDescendants = false
MainContainer.ZIndex = 10
MainContainer.Parent = ScreenGui

-- Main Corner
local MainCorner = Instance.new("UICorner")
MainCorner.CornerRadius = UDim.new(0, 12)
MainCorner.Parent = MainContainer

-- Outer Glow Effect
local GlowEffect = Instance.new("Frame")
GlowEffect.Name = "Glow"
GlowEffect.Size = UDim2.new(1, 6, 1, 6)
GlowEffect.Position = UDim2.new(0, -3, 0, -3)
GlowEffect.BackgroundColor3 = Colors.Accent
GlowEffect.BackgroundTransparency = 0.85
GlowEffect.BorderSizePixel = 0
GlowEffect.ZIndex = 9
GlowEffect.Parent = MainContainer

local GlowCorner = Instance.new("UICorner")
GlowCorner.CornerRadius = UDim.new(0, 14)
GlowCorner.Parent = GlowEffect

-- Drop Shadow
local Shadow1 = Instance.new("ImageLabel")
Shadow1.Name = "Shadow1"
Shadow1.Size = UDim2.new(1, 30, 1, 30)
Shadow1.Position = UDim2.new(0, -15, 0, -15)
Shadow1.BackgroundTransparency = 1
Shadow1.Image = "rbxassetid://6014261993"
Shadow1.ImageColor3 = Colors.Shadow
Shadow1.ImageTransparency = 0.6
Shadow1.ScaleType = Enum.ScaleType.Slice
Shadow1.SliceCenter = Rect.new(49, 49, 49, 49)
Shadow1.ZIndex = 8
Shadow1.Parent = MainContainer

-- ============================================
-- PREMIUM TITLE BAR
-- ============================================

local TitleBar = Instance.new("Frame")
TitleBar.Name = "TitleBar"
TitleBar.Size = UDim2.new(1, 0, 0, 55)
TitleBar.BackgroundColor3 = Colors.SecondaryBg
TitleBar.BorderSizePixel = 0
TitleBar.ZIndex = 11
TitleBar.Parent = MainContainer

local TitleCorner = Instance.new("UICorner")
TitleCorner.CornerRadius = UDim.new(0, 12)
TitleCorner.Parent = TitleBar

-- Title Bar Bottom Border
local TitleBorder = Instance.new("Frame")
TitleBorder.Size = UDim2.new(1, 0, 0, 1)
TitleBorder.Position = UDim2.new(0, 0, 1, 0)
TitleBorder.BackgroundColor3 = Colors.Border
TitleBorder.BorderSizePixel = 0
TitleBorder.ZIndex = 12
TitleBorder.Parent = TitleBar

-- Logo Icon
local LogoIcon = Instance.new("TextLabel")
LogoIcon.Size = UDim2.new(0, 35, 0, 35)
LogoIcon.Position = UDim2.new(0, 15, 0, 10)
LogoIcon.BackgroundColor3 = Colors.Accent
LogoIcon.Text = "⚔"
LogoIcon.TextColor3 = Colors.TextWhite
LogoIcon.Font = Fonts.Body
LogoIcon.TextSize = 18
LogoIcon.BorderSizePixel = 0
LogoIcon.ZIndex = 12
LogoIcon.Parent = TitleBar

local LogoCorner = Instance.new("UICorner")
LogoCorner.CornerRadius = UDim.new(0, 8)
LogoCorner.Parent = LogoIcon

-- Title Text
local TitleText = Instance.new("TextLabel")
TitleText.Size = UDim2.new(0, 150, 0, 30)
TitleText.Position = UDim2.new(0, 60, 0, 8)
TitleText.BackgroundTransparency = 1
TitleText.Text = "MM2 PRO"
TitleText.TextColor3 = Colors.TextWhite
TitleText.Font = Fonts.Title
TitleText.TextSize = 20
TitleText.TextXAlignment = Enum.TextXAlignment.Left
TitleText.ZIndex = 12
TitleText.Parent = TitleBar

-- Version Badge
local VersionBadge = Instance.new("TextLabel")
VersionBadge.Size = UDim2.new(0, 40, 0, 16)
VersionBadge.Position = UDim2.new(0, 215, 0, 14)
VersionBadge.BackgroundColor3 = Colors.Accent
VersionBadge.Text = "v2.0"
VersionBadge.TextColor3 = Colors.TextWhite
VersionBadge.Font = Fonts.Body
VersionBadge.TextSize = 9
VersionBadge.BorderSizePixel = 0
VersionBadge.ZIndex = 12
VersionBadge.Parent = TitleBar

local VersionCorner = Instance.new("UICorner")
VersionCorner.CornerRadius = UDim.new(0, 4)
VersionCorner.Parent = VersionBadge

-- Developer Credit
local DevCredit = Instance.new("TextLabel")
DevCredit.Size = UDim2.new(0, 120, 0, 15)
DevCredit.Position = UDim2.new(0, 60, 0, 35)
DevCredit.BackgroundTransparency = 1
DevCredit.Text = "developed by goodlooking"
DevCredit.TextColor3 = Colors.TextGray
DevCredit.Font = Fonts.Body
DevCredit.TextSize = 9
DevCredit.TextXAlignment = Enum.TextXAlignment.Left
DevCredit.ZIndex = 12
DevCredit.Parent = TitleBar

-- Window Controls
local MinimizeButton = Instance.new("TextButton")
MinimizeButton.Name = "Minimize"
MinimizeButton.Size = UDim2.new(0, 30, 0, 30)
MinimizeButton.Position = UDim2.new(1, -80, 0, 12)
MinimizeButton.BackgroundColor3 = Colors.Border
MinimizeButton.Text = "—"
MinimizeButton.TextColor3 = Colors.TextWhite
MinimizeButton.Font = Fonts.Header
MinimizeButton.TextSize = 16
MinimizeButton.BorderSizePixel = 0
MinimizeButton.ZIndex = 12
MinimizeButton.Parent = TitleBar

local MinCorner = Instance.new("UICorner")
MinCorner.CornerRadius = UDim.new(0, 6)
MinCorner.Parent = MinimizeButton

local CloseButton = Instance.new("TextButton")
CloseButton.Name = "Close"
CloseButton.Size = UDim2.new(0, 30, 0, 30)
CloseButton.Position = UDim2.new(1, -40, 0, 12)
CloseButton.BackgroundColor3 = Colors.Accent
CloseButton.Text = "✕"
CloseButton.TextColor3 = Colors.TextWhite
CloseButton.Font = Fonts.Header
CloseButton.TextSize = 14
CloseButton.BorderSizePixel = 0
CloseButton.ZIndex = 12
CloseButton.Parent = TitleBar

local CloseCorner = Instance.new("UICorner")
CloseCorner.CornerRadius = UDim.new(0, 6)
CloseCorner.Parent = CloseButton

-- Button Hover Effects
MinimizeButton.MouseEnter:Connect(function()
    TweenService:Create(MinimizeButton, TweenInfo.new(0.2), {BackgroundColor3 = Colors.TextGray}):Play()
end)
MinimizeButton.MouseLeave:Connect(function()
    TweenService:Create(MinimizeButton, TweenInfo.new(0.2), {BackgroundColor3 = Colors.Border}):Play()
end)

CloseButton.MouseEnter:Connect(function()
    TweenService:Create(CloseButton, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(255, 80, 80)}):Play()
end)
CloseButton.MouseLeave:Connect(function()
    TweenService:Create(CloseButton, TweenInfo.new(0.2), {BackgroundColor3 = Colors.Accent}):Play()
end)

-- Minimize/Maximize
local isMinimized = false
MinimizeButton.MouseButton1Click:Connect(function()
    isMinimized = not isMinimized
    if isMinimized then
        MainContainer:TweenSize(UDim2.new(0, 620, 0, 55), "Out", "Quart", 0.4, true)
    else
        MainContainer:TweenSize(UDim2.new(0, 620, 0, 420), "Out", "Quart", 0.4, true)
    end
end)

CloseButton.MouseButton1Click:Connect(function()
    MainContainer:TweenSize(UDim2.new(0, 0, 0, 0), "In", "Quart", 0.3, true)
    task.wait(0.3)
    ScreenGui:Destroy()
end)

-- ============================================
-- SIDEBAR NAVIGATION
-- ============================================

local Sidebar = Instance.new("Frame")
Sidebar.Name = "Sidebar"
Sidebar.Size = UDim2.new(0, 140, 1, -55)
Sidebar.Position = UDim2.new(0, 0, 0, 55)
Sidebar.BackgroundColor3 = Colors.SecondaryBg
Sidebar.BorderSizePixel = 0
Sidebar.ZIndex = 11
Sidebar.Parent = MainContainer

-- Sidebar Right Border
local SidebarBorder = Instance.new("Frame")
SidebarBorder.Size = UDim2.new(0, 1, 1, 0)
SidebarBorder.Position = UDim2.new(1, -1, 0, 0)
SidebarBorder.BackgroundColor3 = Colors.Border
SidebarBorder.BorderSizePixel = 0
SidebarBorder.ZIndex = 12
SidebarBorder.Parent = Sidebar

-- Categories Header
local CategoriesHeader = Instance.new("TextLabel")
CategoriesHeader.Size = UDim2.new(1, -20, 0, 25)
CategoriesHeader.Position = UDim2.new(0, 10, 0, 10)
CategoriesHeader.BackgroundTransparency = 1
CategoriesHeader.Text = "CATEGORIES"
CategoriesHeader.TextColor3 = Colors.TextGray
CategoriesHeader.Font = Fonts.Header
CategoriesHeader.TextSize = 9
CategoriesHeader.TextXAlignment = Enum.TextXAlignment.Left
CategoriesHeader.ZIndex = 12
CategoriesHeader.Parent = Sidebar

-- ============================================
-- CONTENT AREA
-- ============================================

local ContentArea = Instance.new("Frame")
ContentArea.Name = "Content"
ContentArea.Size = UDim2.new(1, -140, 1, -55)
ContentArea.Position = UDim2.new(0, 140, 0, 55)
ContentArea.BackgroundColor3 = Colors.MainBg
ContentArea.BorderSizePixel = 0
ContentArea.ClipsDescendants = true
ContentArea.ZIndex = 11
ContentArea.Parent = MainContainer

-- ============================================
-- TAB SYSTEM
-- ============================================

local TabPages = {}
local CurrentTab = nil
local TabButtons = {}

local function CreatePremiumTab(name, icon, order)
    local TabButton = Instance.new("TextButton")
    TabButton.Name = name
    TabButton.Size = UDim2.new(1, -20, 0, 38)
    TabButton.Position = UDim2.new(0, 10, 0, 40 + (order * 45))
    TabButton.BackgroundColor3 = Colors.TabInactive
    TabButton.Text = ""
    TabButton.AutoButtonColor = false
    TabButton.BorderSizePixel = 0
    TabButton.ZIndex = 12
    TabButton.Parent = Sidebar
    
    local TabCorner = Instance.new("UICorner")
    TabCorner.CornerRadius = UDim.new(0, 8)
    TabCorner.Parent = TabButton
    
    -- Icon
    local TabIcon = Instance.new("TextLabel")
    TabIcon.Size = UDim2.new(0, 25, 0, 25)
    TabIcon.Position = UDim2.new(0, 10, 0, 6)
    TabIcon.BackgroundTransparency = 1
    TabIcon.Text = icon
    TabIcon.TextColor3 = Colors.TextGray
    TabIcon.Font = Fonts.Body
    TabIcon.TextSize = 16
    TabIcon.ZIndex = 13
    TabIcon.Name = "Icon"
    TabIcon.Parent = TabButton
    
    -- Label
    local TabLabel = Instance.new("TextLabel")
    TabLabel.Size = UDim2.new(1, -50, 1, 0)
    TabLabel.Position = UDim2.new(0, 40, 0, 0)
    TabLabel.BackgroundTransparency = 1
    TabLabel.Text = name
    TabLabel.TextColor3 = Colors.TextGray
    TabLabel.Font = Fonts.Body
    TabLabel.TextSize = 12
    TabLabel.TextXAlignment = Enum.TextXAlignment.Left
    TabLabel.ZIndex = 13
    TabLabel.Name = "Label"
    TabLabel.Parent = TabButton
    
    -- Active indicator (hidden by default)
    local ActiveIndicator = Instance.new("Frame")
    ActiveIndicator.Size = UDim2.new(0, 3, 0, 20)
    ActiveIndicator.Position = UDim2.new(0, -1, 0.5, -10)
    ActiveIndicator.BackgroundColor3 = Colors.Accent
    ActiveIndicator.BorderSizePixel = 0
    ActiveIndicator.Visible = false
    ActiveIndicator.ZIndex = 14
    ActiveIndicator.Name = "Indicator"
    ActiveIndicator.Parent = TabButton
    
    local IndicatorCorner = Instance.new("UICorner")
    IndicatorCorner.CornerRadius = UDim.new(1, 0)
    IndicatorCorner.Parent = ActiveIndicator
    
    -- Tab Page
    local TabPage = Instance.new("ScrollingFrame")
    TabPage.Name = name
    TabPage.Size = UDim2.new(1, 0, 1, 0)
    TabPage.BackgroundTransparency = 1
    TabPage.BorderSizePixel = 0
    TabPage.ScrollBarThickness = 3
    TabPage.ScrollBarImageColor3 = Colors.Accent
    TabPage.CanvasSize = UDim2.new(0, 0, 0, 700)
    TabPage.Visible = false
    TabPage.ZIndex = 12
    TabPage.Parent = ContentArea
    
    -- Scroll padding
    local UIPadding = Instance.new("UIPadding")
    UIPadding.PaddingTop = UDim.new(0, 10)
    UIPadding.PaddingLeft = UDim.new(0, 10)
    UIPadding.PaddingRight = UDim.new(0, 10)
    UIPadding.Parent = TabPage
    
    table.insert(TabPages, {Button = TabButton, Page = TabPage})
    TabButtons[TabButton] = {Icon = TabIcon, Label = TabLabel, Indicator = ActiveIndicator}
    
    -- Hover effect
    TabButton.MouseEnter:Connect(function()
        if TabPage ~= CurrentTab then
            TweenService:Create(TabButton, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(35, 35, 45)}):Play()
        end
    end)
    TabButton.MouseLeave:Connect(function()
        if TabPage ~= CurrentTab then
            TweenService:Create(TabButton, TweenInfo.new(0.2), {BackgroundColor3 = Colors.TabInactive}):Play()
        end
    end)
    
    -- Click handler
    TabButton.MouseButton1Click:Connect(function()
        for _, tab in pairs(TabPages) do
            tab.Page.Visible = false
            local btnData = TabButtons[tab.Button]
            TweenService:Create(tab.Button, TweenInfo.new(0.3), {BackgroundColor3 = Colors.TabInactive}):Play()
            TweenService:Create(btnData.Icon, TweenInfo.new(0.3), {TextColor3 = Colors.TextGray}):Play()
            TweenService:Create(btnData.Label, TweenInfo.new(0.3), {TextColor3 = Colors.TextGray}):Play()
            btnData.Indicator.Visible = false
        end
        
        TabPage.Visible = true
        CurrentTab = TabPage
        
        local btnData = TabButtons[TabButton]
        TweenService:Create(TabButton, TweenInfo.new(0.3), {BackgroundColor3 = Color3.fromRGB(40, 40, 55)}):Play()
        TweenService:Create(btnData.Icon, TweenInfo.new(0.3), {TextColor3 = Colors.Accent}):Play()
        TweenService:Create(btnData.Label, TweenInfo.new(0.3), {TextColor3 = Colors.TextWhite}):Play()
        btnData.Indicator.Visible = true
    end)
    
    return TabPage
end

-- ============================================
-- PREMIUM UI COMPONENTS
-- ============================================

-- Section Header
local function CreateSection(parent, title, yPos)
    local SectionFrame = Instance.new("Frame")
    SectionFrame.Size = UDim2.new(1, -10, 0, 30)
    SectionFrame.Position = UDim2.new(0, 5, 0, yPos)
    SectionFrame.BackgroundTransparency = 1
    SectionFrame.BorderSizePixel = 0
    SectionFrame.ZIndex = 13
    SectionFrame.Parent = parent
    
    local SectionLine = Instance.new("Frame")
    SectionLine.Size = UDim2.new(0, 3, 0, 15)
    SectionLine.Position = UDim2.new(0, 0, 0.5, -7)
    SectionLine.BackgroundColor3 = Colors.Accent
    SectionLine.BorderSizePixel = 0
    SectionLine.ZIndex = 14
    SectionLine.Parent = SectionFrame
    
    local LineCorner = Instance.new("UICorner")
    LineCorner.CornerRadius = UDim.new(1, 0)
    LineCorner.Parent = SectionLine
    
    local SectionLabel = Instance.new("TextLabel")
    SectionLabel.Size = UDim2.new(1, -15, 1, 0)
    SectionLabel.Position = UDim2.new(0, 10, 0, 0)
    SectionLabel.BackgroundTransparency = 1
    SectionLabel.Text = title
    SectionLabel.TextColor3 = Colors.TextWhite
    SectionLabel.Font = Fonts.Header
    SectionLabel.TextSize = 12
    SectionLabel.TextXAlignment = Enum.TextXAlignment.Left
    SectionLabel.ZIndex = 14
    SectionLabel.Parent = SectionFrame
end

-- Premium Toggle Switch
local function CreatePremiumToggle(parent, name, description, yPos, callback)
    local ToggleFrame = Instance.new("Frame")
    ToggleFrame.Name = name
    ToggleFrame.Size = UDim2.new(1, -10, 0, 55)
    ToggleFrame.Position = UDim2.new(0, 5, 0, yPos)
    ToggleFrame.BackgroundColor3 = Colors.SecondaryBg
    ToggleFrame.BorderSizePixel = 0
    ToggleFrame.ZIndex = 13
    ToggleFrame.Parent = parent
    
    local ToggleCorner = Instance.new("UICorner")
    ToggleCorner.CornerRadius = UDim.new(0, 8)
    ToggleCorner.Parent = ToggleFrame
    
    -- Hover effect border
    local HoverBorder = Instance.new("Frame")
    HoverBorder.Size = UDim2.new(1, 0, 0, 2)
    HoverBorder.Position = UDim2.new(0, 0, 0, 0)
    HoverBorder.BackgroundColor3 = Colors.Accent
    HoverBorder.BackgroundTransparency = 1
    HoverBorder.BorderSizePixel = 0
    HoverBorder.ZIndex = 14
    HoverBorder.Name = "HoverBorder"
    HoverBorder.Parent = ToggleFrame
    
    local BorderCorner = Instance.new("UICorner")
    BorderCorner.CornerRadius = UDim.new(0, 8)
    BorderCorner.Parent = HoverBorder
    
    -- Info Icon
    local InfoIcon = Instance.new("Frame")
    InfoIcon.Size = UDim2.new(0, 35, 0, 35)
    InfoIcon.Position = UDim2.new(0, 10, 0.5, -17)
    InfoIcon.BackgroundColor3 = Color3.fromRGB(40, 40, 55)
    InfoIcon.BorderSizePixel = 0
    InfoIcon.ZIndex = 14
    InfoIcon.Parent = ToggleFrame
    
    local InfoCorner = Instance.new("UICorner")
    InfoCorner.CornerRadius = UDim.new(0, 8)
    InfoCorner.Parent = InfoIcon
    
    local InfoText = Instance.new("TextLabel")
    InfoText.Size = UDim2.new(1, 0, 1, 0)
    InfoText.BackgroundTransparency = 1
    InfoText.Text = "⚡"
    InfoText.TextColor3 = Colors.Accent
    InfoText.Font = Fonts.Body
    InfoText.TextSize = 16
    InfoText.ZIndex = 15
    InfoText.Parent = InfoIcon
    
    -- Labels
    local ToggleName = Instance.new("TextLabel")
    ToggleName.Size = UDim2.new(0.55, -60, 0.5, 0)
    ToggleName.Position = UDim2.new(0, 55, 0.1, 0)
    ToggleName.BackgroundTransparency = 1
    ToggleName.Text = name
    ToggleName.TextColor3 = Colors.TextWhite
    ToggleName.Font = Fonts.Header
    ToggleName.TextSize = 12
    ToggleName.TextXAlignment = Enum.TextXAlignment.Left
    ToggleName.ZIndex = 14
    ToggleName.Parent = ToggleFrame
    
    local ToggleDesc = Instance.new("TextLabel")
    ToggleDesc.Size = UDim2.new(0.55, -60, 0.4, 0)
    ToggleDesc.Position = UDim2.new(0, 55, 0.5, 0)
    ToggleDesc.BackgroundTransparency = 1
    ToggleDesc.Text = description
    ToggleDesc.TextColor3 = Colors.TextGray
    ToggleDesc.Font = Fonts.Body
    ToggleDesc.TextSize = 10
    ToggleDesc.TextXAlignment = Enum.TextXAlignment.Left
    ToggleDesc.ZIndex = 14
    ToggleDesc.Parent = ToggleFrame
    
    -- Premium Toggle
    local ToggleButton = Instance.new("TextButton")
    ToggleButton.Size = UDim2.new(0, 48, 0, 26)
    ToggleButton.Position = UDim2.new(0.88, 0, 0.5, -13)
    ToggleButton.BackgroundColor3 = Colors.ToggleOff
    ToggleButton.Text = ""
    ToggleButton.BorderSizePixel = 0
    ToggleButton.AutoButtonColor = false
    ToggleButton.ZIndex = 14
    ToggleButton.Parent = ToggleFrame
    
    local ToggleBtnCorner = Instance.new("UICorner")
    ToggleBtnCorner.CornerRadius = UDim.new(1, 0)
    ToggleBtnCorner.Parent = ToggleButton
    
    local ToggleDot = Instance.new("Frame")
    ToggleDot.Size = UDim2.new(0, 20, 0, 20)
    ToggleDot.Position = UDim2.new(0, 3, 0, 3)
    ToggleDot.BackgroundColor3 = Colors.TextWhite
    ToggleDot.BorderSizePixel = 0
    ToggleDot.ZIndex = 15
    ToggleDot.Parent = ToggleButton
    
    local DotCorner = Instance.new("UICorner")
    DotCorner.CornerRadius = UDim.new(1, 0)
    DotCorner.Parent = ToggleDot
    
    -- Status text
    local StatusText = Instance.new("TextLabel")
    StatusText.Size = UDim2.new(0, 40, 0, 15)
    StatusText.Position = UDim2.new(1, -95, 0.5, 10)
    StatusText.BackgroundTransparency = 1
    StatusText.Text = "OFF"
    StatusText.TextColor3 = Colors.TextGray
    StatusText.Font = Fonts.Body
    StatusText.TextSize = 8
    StatusText.TextXAlignment = Enum.TextXAlignment.Right
    StatusText.ZIndex = 14
    StatusText.Parent = ToggleFrame
    
    local enabled = false
    
    -- Hover effects
    ToggleFrame.MouseEnter:Connect(function()
        TweenService:Create(HoverBorder, TweenInfo.new(0.3), {BackgroundTransparency = 0}):Play()
    end)
    ToggleFrame.MouseLeave:Connect(function()
        TweenService:Create(HoverBorder, TweenInfo.new(0.3), {BackgroundTransparency = 1}):Play()
    end)
    
    ToggleButton.MouseButton1Click:Connect(function()
        enabled = not enabled
        if enabled then
            TweenService:Create(ToggleButton, TweenInfo.new(0.3), {BackgroundColor3 = Colors.ToggleOn}):Play()
            TweenService:Create(ToggleDot, TweenInfo.new(0.3), {Position = UDim2.new(0, 25, 0, 3)}):Play()
            TweenService:Create(InfoIcon, TweenInfo.new(0.3), {BackgroundColor3 = Color3.fromRGB(50, 205, 50)}):Play()
            TweenService:Create(InfoText, TweenInfo.new(0.3), {TextColor3 = Colors.TextWhite}):Play()
            StatusText.Text = "ON"
            TweenService:Create(StatusText, TweenInfo.new(0.3), {TextColor3 = Colors.Green}):Play()
        else
            TweenService:Create(ToggleButton, TweenInfo.new(0.3), {BackgroundColor3 = Colors.ToggleOff}):Play()
            TweenService:Create(ToggleDot, TweenInfo.new(0.3), {Position = UDim2.new(0, 3, 0, 3)}):Play()
            TweenService:Create(InfoIcon, TweenInfo.new(0.3), {BackgroundColor3 = Color3.fromRGB(40, 40, 55)}):Play()
            TweenService:Create(InfoText, TweenInfo.new(0.3), {TextColor3 = Colors.Accent}):Play()
            StatusText.Text = "OFF"
            TweenService:Create(StatusText, TweenInfo.new(0.3), {TextColor3 = Colors.TextGray}):Play()
        end
        callback(enabled)
    end)
    
    return ToggleFrame
end

-- ============================================
-- ROLE DETECTION SYSTEM
-- ============================================

local function getPlayerRole(player)
    if player.Backpack then
        if player.Backpack:FindFirstChild("Knife") then
            return "Murderer"
        elseif player.Backpack:FindFirstChild("Gun") or player.Backpack:FindFirstChild("Revolver") then
            return "Sheriff"
        end
    end
    if player.Character then
        if player.Character:FindFirstChild("Knife") then
            return "Murderer"
        elseif player.Character:FindFirstChild("Gun") or player.Character:FindFirstChild("Revolver") then
            return "Sheriff"
        end
    end
    return "Innocent"
end

-- ============================================
-- AIMBOT BUTTON SYSTEM
-- ============================================

local AimButton = nil
local aimActive = false
local isDraggingButton = false
local dragOffset = Vector2.new(0, 0)

local function shootMurderer()
    pcall(function()
        if not aimActive then return end
        
        local localChar = LocalPlayer.Character
        if not localChar then return end
        
        if getPlayerRole(LocalPlayer) ~= "Sheriff" then return end
        
        local nearestMurderer = nil
        local minDist = math.huge
        local localRoot = localChar:FindFirstChild("HumanoidRootPart")
        
        if not localRoot then return end
        
        for _, player in pairs(Players:GetPlayers()) do
            if player ~= LocalPlayer and player.Character then
                if getPlayerRole(player) == "Murderer" then
                    local targetRoot = player.Character:FindFirstChild("HumanoidRootPart")
                    if targetRoot then
                        local dist = (localRoot.Position - targetRoot.Position).Magnitude
                        if dist < minDist then
                            minDist = dist
                            nearestMurderer = player
                        end
                    end
                end
            end
        end
        
        if not nearestMurderer or not nearestMurderer.Character then return end
        
        local gun = LocalPlayer.Backpack:FindFirstChild("Gun") or LocalPlayer.Backpack:FindFirstChild("Revolver")
        local equippedGun = localChar:FindFirstChild("Gun") or localChar:FindFirstChild("Revolver")
        
        if not equippedGun and gun then
            local humanoid = localChar:FindFirstChild("Humanoid")
            if humanoid then humanoid:EquipTool(gun) task.wait(0.15) end
        end
        
        local targetPart = nearestMurderer.Character:FindFirstChild("Head") or nearestMurderer.Character:FindFirstChild("HumanoidRootPart")
        if not targetPart then return end
        
        if localRoot then
            local lookDir = (targetPart.Position - localRoot.Position).Unit
            localRoot.CFrame = CFrame.lookAt(localRoot.Position, localRoot.Position + lookDir)
        end
        
        equippedGun = localChar:FindFirstChild("Gun") or localChar:FindFirstChild("Revolver")
        if equippedGun then
            pcall(function()
                for _, child in pairs(equippedGun:GetChildren()) do
                    if child:IsA("RemoteEvent") then
                        child:FireServer(targetPart.Position, targetPart)
                    end
                end
            end)
            pcall(function()
                local humanoid = nearestMurderer.Character:FindFirstChild("Humanoid")
                if humanoid then humanoid.Health = 0 end
            end)
        end
    end)
end

local function CreateAimButton()
    if AimButton then AimButton:Destroy() end
    
    AimButton = Instance.new("Frame")
    AimButton.Name = "AimButton"
    AimButton.Size = UDim2.new(0, 90, 0, 90)
    AimButton.Position = UDim2.new(0.7, -45, 0.5, -45)
    AimButton.BackgroundTransparency = 1
    AimButton.BorderSizePixel = 0
    AimButton.ZIndex = 100
    AimButton.Parent = ScreenGui
    
    -- Outer ring
    local OuterRing = Instance.new("Frame")
    OuterRing.Size = UDim2.new(0, 90, 0, 90)
    OuterRing.BackgroundColor3 = Colors.TextWhite
    OuterRing.BackgroundTransparency = 0.75
    OuterRing.BorderSizePixel = 0
    OuterRing.ZIndex = 101
    OuterRing.Parent = AimButton
    
    local OuterCorner = Instance.new("UICorner")
    OuterCorner.CornerRadius = UDim.new(1, 0)
    OuterCorner.Parent = OuterRing
    
    -- Inner ring
    local InnerRing = Instance.new("Frame")
    InnerRing.Size = UDim2.new(0, 60, 0, 60)
    InnerRing.Position = UDim2.new(0.5, -30, 0.5, -30)
    InnerRing.BackgroundColor3 = Colors.Accent
    InnerRing.BackgroundTransparency = 0.8
    InnerRing.BorderSizePixel = 0
    InnerRing.ZIndex = 102
    InnerRing.Parent = AimButton
    
    local InnerCorner = Instance.new("UICorner")
    InnerCorner.CornerRadius = UDim.new(1, 0)
    InnerCorner.Parent = InnerRing
    
    -- Crosshair lines
    for i = 1, 4 do
        local line = Instance.new("Frame")
        line.Size = UDim2.new(0, 2, 0, 18)
        line.Position = UDim2.new(0.5, -1, 0, 3)
        line.BackgroundColor3 = Colors.Accent
        line.BorderSizePixel = 0
        line.ZIndex = 103
        line.Rotation = (i - 1) * 90
        line.Parent = AimButton
    end
    
    -- Center dot
    local CenterDot = Instance.new("Frame")
    CenterDot.Size = UDim2.new(0, 6, 0, 6)
    CenterDot.Position = UDim2.new(0.5, -3, 0.5, -3)
    CenterDot.BackgroundColor3 = Colors.TextWhite
    CenterDot.BorderSizePixel = 0
    CenterDot.ZIndex = 104
    CenterDot.Parent = AimButton
    
    local DotCorner = Instance.new("UICorner")
    DotCorner.CornerRadius = UDim.new(1, 0)
    DotCorner.Parent = CenterDot
    
    -- Click button
    local ClickButton = Instance.new("TextButton")
    ClickButton.Size = UDim2.new(1, 0, 1, 0)
    ClickButton.BackgroundTransparency = 1
    ClickButton.Text = ""
    ClickButton.BorderSizePixel = 0
    ClickButton.ZIndex = 105
    ClickButton.Parent = AimButton
    
    ClickButton.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 then
            isDraggingButton = true
            dragOffset = input.Position - Vector2.new(AimButton.AbsolutePosition.X, AimButton.AbsolutePosition.Y)
        end
    end)
    
    ClickButton.InputEnded:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 then
            local currentPos = Vector2.new(AimButton.AbsolutePosition.X, AimButton.AbsolutePosition.Y)
            local startPos = input.Position - dragOffset
            if (currentPos - startPos).Magnitude < 5 then
                shootMurderer()
            end
            isDraggingButton = false
        end
    end)
    
    UserInputService.InputChanged:Connect(function(input)
        if isDraggingButton and input.UserInputType == Enum.UserInputType.MouseMovement then
            local newPos = input.Position - dragOffset
            AimButton.Position = UDim2.new(0, newPos.X, 0, newPos.Y)
        end
    end)
end

-- ============================================
-- CREATE TABS
-- ============================================

local CombatTab = CreatePremiumTab("Combat", "⚔", 0)
local VisualTab = CreatePremiumTab("Visuals", "👁", 1)
local FarmTab = CreatePremiumTab("Farming", "💰", 2)
local MiscTab = CreatePremiumTab("Misc", "🔧", 3)

-- Activate first tab
if #TabPages > 0 then
    TabPages[1].Page.Visible = true
    CurrentTab = TabPages[1].Page
    local btnData = TabButtons[TabPages[1].Button]
    btnData.Indicator.Visible = true
    TweenService:Create(TabPages[1].Button, TweenInfo.new(0), {BackgroundColor3 = Color3.fromRGB(40, 40, 55)}):Play()
    TweenService:Create(btnData.Icon, TweenInfo.new(0), {TextColor3 = Colors.Accent}):Play()
    TweenService:Create(btnData.Label, TweenInfo.new(0), {TextColor3 = Colors.TextWhite}):Play()
end

-- ============================================
-- COMBAT MODULES
-- ============================================

local active = {}
local connections = {}
local playerHighlights = {}

CreateSection(CombatTab, "COMBAT MODULES", 5)

CreatePremiumToggle(CombatTab, "Kill Murderer", "Instantly eliminates all murderers", 40, function(state)
    active.killMurder = state
    if state then
        connections.killMurder = RunService.Heartbeat:Connect(function()
            pcall(function()
                for _, v in pairs(Players:GetPlayers()) do
                    if v ~= LocalPlayer and v.Character and v.Character:FindFirstChild("Humanoid") then
                        if getPlayerRole(v) == "Murderer" then
                            v.Character.Humanoid.Health = 0
                        end
                    end
                end
            end)
        end)
    else
        if connections.killMurder then connections.killMurder:Disconnect() end
    end
end)

CreatePremiumToggle(CombatTab, "Shoot Murderer", "Aimbot for sheriff - drag button to move", 100, function(state)
    aimActive = state
    if state then CreateAimButton()
    else if AimButton then AimButton:Destroy() AimButton = nil end end
end)

CreatePremiumToggle(CombatTab, "Fling Players", "Launch all players into the air", 160, function(state)
    active.fling = state
    if state then
        connections.fling = RunService.Heartbeat:Connect(function()
            pcall(function()
                for _, v in pairs(Players:GetPlayers()) do
                    if v ~= LocalPlayer and v.Character then
                        local root = v.Character:FindFirstChild("HumanoidRootPart")
                        if root then
                            root.Velocity = Vector3.new(math.random(-10000, 10000), math.random(5000, 20000), math.random(-10000, 10000))
                        end
                    end
                end
            end)
        end)
    else
        if connections.fling then connections.fling:Disconnect() end
    end
end)

CreatePremiumToggle(CombatTab, "God Mode", "Complete damage immunity", 220, function(state)
    active.god = state
    if state then
        connections.god = RunService.Heartbeat:Connect(function()
            pcall(function()
                if LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("Humanoid") then
                    LocalPlayer.Character.Humanoid.Health = LocalPlayer.Character.Humanoid.MaxHealth
                end
            end)
        end)
    else
        if connections.god then connections.god:Disconnect() end
    end
end)

CreatePremiumToggle(CombatTab, "One Shot Kill", "Kill anyone with one hit", 280, function(state)
    active.oneshot = state
end)

-- ============================================
-- VISUAL MODULES
-- ============================================

CreateSection(VisualTab, "VISUAL MODULES", 5)

CreatePremiumToggle(VisualTab, "Player ESP", "See players through walls with roles", 40, function(state)
    active.esp = state
    if state then
        connections.esp = RunService.RenderStepped:Connect(function()
            pcall(function()
                for _, player in pairs(Players:GetPlayers()) do
                    if player ~= LocalPlayer and player.Character then
                        local role = getPlayerRole(player)
                        local color
                        
                        if role == "Murderer" then
                            color = Color3.fromRGB(255, 50, 50)
                        elseif role == "Sheriff" then
                            color = Color3.fromRGB(30, 144, 255)
                        else
                            color = Color3.fromRGB(50, 205, 50)
                        end
                        
                        local highlight = player.Character:FindFirstChild("RoleESP")
                        if not highlight then
                            highlight = Instance.new("Highlight")
                            highlight.Name = "RoleESP"
                            highlight.Adornee = player.Character
                            highlight.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop
                            highlight.FillTransparency = 0.4
                            highlight.OutlineTransparency = 0.2
                            highlight.Parent = player.Character
                        end
                        
                        highlight.FillColor = color
                        highlight.OutlineColor = color
                        
                        local head = player.Character:FindFirstChild("Head")
                        if head and not head:FindFirstChild("RoleTag") then
                            local billboard = Instance.new("BillboardGui")
                            billboard.Name = "RoleTag"
                            billboard.Size = UDim2.new(0, 200, 0, 40)
                            billboard.StudsOffset = Vector3.new(0, 3, 0)
                            billboard.AlwaysOnTop = true
                            billboard.Parent = head
                            
                            local tag = Instance.new("TextLabel")
                            tag.Size = UDim2.new(1, 0, 1, 0)
                            tag.BackgroundTransparency = 1
                            tag.Text = "🎯 " .. player.Name .. " | " .. role
                            tag.TextColor3 = color
                            tag.Font = Fonts.Header
                            tag.TextSize = 12
                            tag.Parent = billboard
                        end
                        
                        playerHighlights[player] = highlight
                    end
                end
            end)
        end)
    else
        if connections.esp then connections.esp:Disconnect() end
        for player, highlight in pairs(playerHighlights) do
            if highlight then highlight:Destroy() end
            if player.Character then
                local head = player.Character:FindFirstChild("Head")
                if head and head:FindFirstChild("RoleTag") then head.RoleTag:Destroy() end
            end
        end
        playerHighlights = {}
    end
end)

CreatePremiumToggle(VisualTab, "Coin ESP", "Highlight all coins on map", 100, function(state)
    active.coinESP = state
    if state then
        connections.coinESP = RunService.RenderStepped:Connect(function()
            pcall(function()
                for _, v in pairs(workspace:GetChildren()) do
                    if v.Name == "Coin" and v:IsA("BasePart") and not v:FindFirstChild("CoinESP") then
                        local h = Instance.new("Highlight")
                        h.Name = "CoinESP"
                        h.Adornee = v
                        h.FillColor = Colors.Gold
                        h.FillTransparency = 0.3
                        h.OutlineColor = Colors.TextWhite
                        h.OutlineTransparency = 0.5
                        h.Parent = v
                    end
                end
            end)
        end)
    else
        if connections.coinESP then connections.coinESP:Disconnect() end
        for _, v in pairs(workspace:GetChildren()) do
            if v:FindFirstChild("CoinESP") then v.CoinESP:Destroy() end
        end
    end
end)

CreatePremiumToggle(VisualTab, "Full Bright", "Maximum map brightness", 160, function(state)
    if state then
        game.Lighting.Brightness = 3
        game.Lighting.ClockTime = 14
        game.Lighting.FogEnd = 999999
        game.Lighting.OutdoorAmbient = Color3.fromRGB(128, 128, 128)
    else
        game.Lighting.Brightness = 1
        game.Lighting.ClockTime = 14
        game.Lighting.FogEnd = 500
        game.Lighting.OutdoorAmbient = Color3.fromRGB(70, 70, 70)
    end
end)

CreatePremiumToggle(VisualTab, "Chams", "X-ray vision for players", 220, function(state)
    active.chams = state
    if state then
        for _, v in pairs(Players:GetPlayers()) do
            if v ~= LocalPlayer and v.Character then
                for _, part in pairs(v.Character:GetDescendants()) do
                    if part:IsA("BasePart") and part.Transparency < 0.5 then
                        part.LocalTransparencyModifier = 0.4
                    end
                end
            end
        end
    else
        for _, v in pairs(Players:GetPlayers()) do
            if v ~= LocalPlayer and v.Character then
                for _, part in pairs(v.Character:GetDescendants()) do
                    if part:IsA("BasePart") then
                        part.LocalTransparencyModifier = 0
                    end
                end
            end
        end
    end
end)

-- ============================================
-- FARMING MODULES
-- ============================================

CreateSection(FarmTab, "FARMING MODULES", 5)

CreatePremiumToggle(FarmTab, "Auto Farm Coins", "Automatically collect nearest coins", 40, function(state)
    active.farm = state
    if state then
        connections.farm = RunService.Heartbeat:Connect(function()
            pcall(function()
                if LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart") then
                    local root = LocalPlayer.Character.HumanoidRootPart
                    local nearest = nil
                    local minDist = math.huge
                    for _, v in pairs(workspace:GetDescendants()) do
                        if v:IsA("BasePart") and v.Name == "Coin" then
                            local dist = (root.Position - v.Position).Magnitude
                            if dist < minDist then
                                minDist = dist
                                nearest = v
                            end
                        end
                    end
                    if nearest then
                        root.CFrame = nearest.CFrame + Vector3.new(0, 3, 0)
                    end
                end
            end)
        end)
    else
        if connections.farm then connections.farm:Disconnect() end
    end
end)

CreatePremiumToggle(FarmTab, "Auto Collect Guns", "Pick up all dropped weapons", 100, function(state)
    active.collectGun = state
    if state then
        connections.collectGun = RunService.Heartbeat:Connect(function()
            pcall(function()
                for _, v in pairs(workspace:GetDescendants()) do
                    if v:IsA("Tool") and (v.Name == "Gun" or v.Name == "Revolver") and v:FindFirstChild("Handle") then
                        if LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart") then
                            firetouchinterest(LocalPlayer.Character.HumanoidRootPart, v.Handle, 0)
                            firetouchinterest(LocalPlayer.Character.HumanoidRootPart, v.Handle, 1)
                        end
                    end
                end
            end)
        end)
    else
        if connections.collectGun then connections.collectGun:Disconnect() end
    end
end)

CreatePremiumToggle(FarmTab, "Auto Revive", "Auto revive when downed", 160, function(state)
    active.autoRevive = state
end)

-- ============================================
-- MISC MODULES
-- ============================================

CreateSection(MiscTab, "MISCELLANEOUS", 5)

CreatePremiumToggle(MiscTab, "Speed Boost", "2x movement speed", 40, function(state)
    active.speed = state
    if state then
        pcall(function()
            if LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("Humanoid") then
                LocalPlayer.Character.Humanoid.WalkSpeed = 32
            end
        end)
        connections.speed = LocalPlayer.CharacterAdded:Connect(function(char)
            task.wait(0.5)
            pcall(function()
                if char:FindFirstChild("Humanoid") then char.Humanoid.WalkSpeed = 32 end
            end)
        end)
    else
        pcall(function()
            if LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("Humanoid") then
                LocalPlayer.Character.Humanoid.WalkSpeed = 16
            end
        end)
        if connections.speed then connections.speed:Disconnect() end
    end
end)

CreatePremiumToggle(MiscTab, "NoClip", "Walk through walls", 100, function(state)
    active.noclip = state
    if state then
        connections.noclip = RunService.Stepped:Connect(function()
            pcall(function()
                if LocalPlayer.Character then
                    for _, part in pairs(LocalPlayer.Character:GetDescendants()) do
                        if part:IsA("BasePart") then part.CanCollide = false end
                    end
                end
            end)
        end)
    else
        if connections.noclip then connections.noclip:Disconnect() end
    end
end)

CreatePremiumToggle(MiscTab, "Infinite Jump", "Jump unlimited times", 160, function(state)
    active.infJump = state
    if state then
        connections.infJump = UserInputService.JumpRequest:Connect(function()
            pcall(function()
                if LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("Humanoid") then
                    LocalPlayer.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
                end
            end)
        end)
    else
        if connections.infJump then connections.infJump:Disconnect() end
    end
end)

CreatePremiumToggle(MiscTab, "Fly", "Enable flying mode", 220, function(state)
    active.fly = state
    if state then
        connections.fly = RunService.Heartbeat:Connect(function()
            pcall(function()
                if LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart") then
                    LocalPlayer.Character.HumanoidRootPart.Velocity = Vector3.new(0, 50, 0)
                end
            end)
        end)
    else
        if connections.fly then connections.fly:Disconnect() end
    end
end)

-- ============================================
-- PREMIUM WATERMARK
-- ============================================

local WatermarkFrame = Instance.new("Frame")
WatermarkFrame.Size = UDim2.new(0, 250, 0, 30)
WatermarkFrame.Position = UDim2.new(1, -260, 1, -40)
WatermarkFrame.BackgroundColor3 = Colors.SecondaryBg
WatermarkFrame.BackgroundTransparency = 0.3
WatermarkFrame.BorderSizePixel = 0
WatermarkFrame.ZIndex = 200
WatermarkFrame.Parent = ScreenGui

local WatermarkCorner = Instance.new("UICorner")
WatermarkCorner.CornerRadius = UDim.new(0, 6)
WatermarkCorner.Parent = WatermarkFrame

local WatermarkText = Instance.new("TextLabel")
WatermarkText.Size = UDim2.new(1, -10, 1, 0)
WatermarkText.Position = UDim2.new(0, 5, 0, 0)
WatermarkText.BackgroundTransparency = 1
WatermarkText.Text = "MM2 PRO | goodlooking | FPS: --"
WatermarkText.TextColor3 = Colors.TextWhite
WatermarkText.Font = Fonts.Body
WatermarkText.TextSize = 11
WatermarkText.TextXAlignment = Enum.TextXAlignment.Left
WatermarkText.ZIndex = 201
WatermarkText.Parent = WatermarkFrame

spawn(function()
    while task.wait(1) do
        pcall(function()
            WatermarkText.Text = "MM2 PRO | goodlooking | FPS: " .. math.floor(1 / (task.wait() + 0.0001))
        end)
    end
end)

-- ============================================
-- NOTIFICATION SYSTEM
-- ============================================

local function ShowNotification(title, message, duration)
    local NotifFrame = Instance.new("Frame")
    NotifFrame.Size = UDim2.new(0, 300, 0, 60)
    NotifFrame.Position = UDim2.new(1, -310, 0, 20)
    NotifFrame.BackgroundColor3 = Colors.SecondaryBg
    NotifFrame.BorderSizePixel = 0
    NotifFrame.ZIndex = 300
    NotifFrame.Parent = ScreenGui
    
    local NotifCorner = Instance.new("UICorner")
    NotifCorner.CornerRadius = UDim.new(0, 8)
    NotifCorner.Parent = NotifFrame
    
    local AccentBar = Instance.new("Frame")
    AccentBar.Size = UDim2.new(0, 3, 1, 0)
    AccentBar.BackgroundColor3 = Colors.Accent
    AccentBar.BorderSizePixel = 0
    AccentBar.ZIndex = 301
    AccentBar.Parent = NotifFrame
    
    local NotifTitle = Instance.new("TextLabel")
    NotifTitle.Size = UDim2.new(1, -20, 0, 25)
    NotifTitle.Position = UDim2.new(0, 15, 0, 5)
    NotifTitle.BackgroundTransparency = 1
    NotifTitle.Text = title
    NotifTitle.TextColor3 = Colors.TextWhite
    NotifTitle.Font = Fonts.Header
    NotifTitle.TextSize = 13
    NotifTitle.TextXAlignment = Enum.TextXAlignment.Left
    NotifTitle.ZIndex = 301
    NotifTitle.Parent = NotifFrame
    
    local NotifMsg = Instance.new("TextLabel")
    NotifMsg.Size = UDim2.new(1, -20, 0, 20)
    NotifMsg.Position = UDim2.new(0, 15, 0, 30)
    NotifMsg.BackgroundTransparency = 1
    NotifMsg.Text = message
    NotifMsg.TextColor3 = Colors.TextGray
    NotifMsg.Font = Fonts.Body
    NotifMsg.TextSize = 11
    NotifMsg.TextXAlignment = Enum.TextXAlignment.Left
    NotifMsg.ZIndex = 301
    NotifMsg.Parent = NotifFrame
    
    NotifFrame:TweenPosition(UDim2.new(1, -310, 0, -70), "In", "Back", 0.5, true)
    task.wait(0.5)
    NotifFrame:TweenPosition(UDim2.new(1, -310, 0, 20), "Out", "Quad", 0.3, true)
    task.wait(duration or 3)
    NotifFrame:TweenPosition(UDim2.new(1, 10, 0, 20), "In", "Quad", 0.3, true)
    task.wait(0.3)
    NotifFrame:Destroy()
end

-- ============================================
-- DRAG SYSTEM
-- ============================================

local dragging = false
local dragStart = nil
local startPos = nil

TitleBar.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        dragging = true
        dragStart = input.Position
        startPos = MainContainer.Position
    end
end)

TitleBar.InputEnded:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        dragging = false
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then
        local delta = input.Position - dragStart
        MainContainer.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
    end
end)

-- ============================================
-- AUTO RE-INJECT
-- ============================================

LocalPlayer.CharacterAdded:Connect(function()
    task.wait(1)
    if ScreenGui and not ScreenGui.Parent then
        ScreenGui.Parent = CoreGui
    end
end)

-- ============================================
-- STARTUP NOTIFICATION
-- ============================================

ShowNotification("✅ MM2 PRO v2.0", "Premium script loaded successfully!", 4)
print("[MM2 PRO] Premium script loaded!")
