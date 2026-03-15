local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local TabButtons = Instance.new("Frame")
local ContentFrame = Instance.new("Frame")
local OpenIcon = Instance.new("ImageButton")

-- Cấu hình hệ thống để không bị đè
ScreenGui.Parent = game:GetService("CoreGui")
ScreenGui.Name = "ShadowKen_MultiHub"
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Global

-- 1. NÚT MẶT CƯỜI (ICON) - LUÔN NỔI TRÊN CÙNG
OpenIcon.Parent = ScreenGui
OpenIcon.Size = UDim2.new(0, 55, 0, 55)
OpenIcon.Position = UDim2.new(0.05, 0, 0.4, 0)
OpenIcon.Image = "rbxassetid://6034284752"
OpenIcon.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
OpenIcon.Draggable = true
Instance.new("UICorner", OpenIcon).CornerRadius = UDim.new(0, 10)

-- 2. KHUNG MENU CHÍNH (CÓ THỂ KÉO)
MainFrame.Parent = ScreenGui
MainFrame.Size = UDim2.new(0, 400, 0, 280)
MainFrame.Position = UDim2.new(0.3, 0, 0.3, 0)
MainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
MainFrame.Visible = false
MainFrame.Active = true
MainFrame.Draggable = true -- Kéo khung menu
Instance.new("UICorner", MainFrame)

-- Thanh Tab bên trái
TabButtons.Parent = MainFrame
TabButtons.Size = UDim2.new(0, 100, 1, 0)
TabButtons.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Instance.new("UICorner", TabButtons)

-- Khung nội dung bên phải (Có thanh cuộn)
ContentFrame.Parent = MainFrame
ContentFrame.Position = UDim2.new(0, 105, 0, 5)
ContentFrame.Size = UDim2.new(1, -110, 1, -10)
ContentFrame.BackgroundTransparency = 1

local function createTab(name, pos)
    local btn = Instance.new("TextButton")
    btn.Parent = TabButtons
    btn.Size = UDim2.new(1, -10, 0, 35)
    btn.Position = UDim2.new(0, 5, 0, pos)
    btn.Text = name
    btn.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    Instance.new("UICorner", btn)
    
    local scroll = Instance.new("ScrollingFrame")
    scroll.Parent = ContentFrame
    scroll.Size = UDim2.new(1, 0, 1, 0)
    scroll.BackgroundTransparency = 1
    scroll.Visible = false
    scroll.CanvasSize = UDim2.new(0, 0, 2, 0) -- Kéo lên xuống
    scroll.ScrollBarThickness = 4
    
    local layout = Instance.new("UIListLayout", scroll)
    layout.Padding = UDim.new(0, 5)
    
    btn.MouseButton1Click:Connect(function()
        for _, v in pairs(ContentFrame:GetChildren()) do v.Visible = false end
        scroll.Visible = true
    end)
    return scroll
end

local function addScript(parent, name, link)
    local b = Instance.new("TextButton")
    b.Parent = parent
    b.Size = UDim2.new(1, -10, 0, 40)
    b.Text = name
    b.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
    b.TextColor3 = Color3.fromRGB(255, 255, 255)
    Instance.new("UICorner", b)
    b.MouseButton1Click:Connect(function()
        loadstring(game:HttpGet(link))()
    end)
end

-- TẠO CÁC MỤC (TABS)
local bfTab = createTab("Blox Fruits", 10)
local fischTab = createTab("Fisch It", 50)
local tycoonTab = createTab("Tycoon", 90)

-- 1. BLOX FRUITS
addScript(bfTab, "Quantum Onyx", "https://raw.githubusercontent.com/flazhy/QuantumOnyx/refs/heads/main/QuantumOnyx.lua")
addScript(bfTab, "Gravity Hub", "https://raw.githubusercontent.com/Dev-GravityHub/BloxFruit/refs/heads/main/Main.lua")
addScript(bfTab, "AnDepZai Hub", "https://raw.githubusercontent.com/longhihilonghihi-hub/AnDepZaiHubV1/refs/heads/main/AnDepZaiHub.Lua")
addScript(bfTab, "Maru Hub V1", "https://raw.githubusercontent.com/longhihilonghihi-hub/MaruHubV1/refs/heads/main/MainV1.Lua")
addScript(bfTab, "LongHiHi V3.2", "https://raw.githubusercontent.com/longhihilonghihi-hub/Devs-LongHiHiV3.2/refs/heads/main/MainV3-UltraAttack.Lua")

-- 2. FISCH (Fishing Simulator)
addScript(fischTab, "Fisch It Hub", "https://raw.githubusercontent.com/3345-c409/-fisch-/refs/heads/main/fisch.lua")
addScript(fischTab, "Zane Hub", "https://raw.githubusercontent.com/Zane9999/ZaneHub/main/Fisch.lua")

-- 3. TYCOON & OTHERS
addScript(tycoonTab, "Sell PC Tycoon", "https://raw.githubusercontent.com/ToraIsMe/ToraIsMe/main/0PC")
addScript(tycoonTab, "Ultra Tycoon", "https://raw.githubusercontent.com/HibaHub/Hiba/main/Tycoon.lua")
addScript(tycoonTab, "Auto Prove Mom Wrong", "https://raw.githubusercontent.com/ToraIsMe/ToraIsMe/main/0ProveMomWrong")

-- Đóng/Mở
OpenIcon.MouseButton1Click:Connect(function() MainFrame.Visible = not MainFrame.Visible end)
bfTab.Visible = true -- Hiện mặc định tab Blox Fruit
