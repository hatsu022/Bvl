                            local auraClone = obj:Clone()
                            auraClone.Parent = part
                            auraClone.Color = ColorSequence.new(color)
                            game.Debris:AddItem(auraClone, duration)
                        end
                    end
                end
            end
        end

        specAura(p1, p2Name, p3Duration, p4Color)

        local function specEyes(char, duration, color)
            if char and char:FindFirstChild("Head") then
                local eyesEffect = game.ReplicatedStorage.Assets.EffectParts.SpecEyes:Clone()
                for _, obj in ipairs(eyesEffect:GetChildren()) do
                    local trail = obj:FindFirstChild("Trail")
                    local particleEmitter = obj:FindFirstChild("ParticleEmitter")
                    if trail then
                        trail.Color = ColorSequence.new(color)
                    end
                    if particleEmitter then
                        particleEmitter.Color = ColorSequence.new(color)
                    end
                    obj.Parent = char.Head
                    game.Debris:AddItem(obj, duration)
                end
            end
        end

        specEyes(p1, p3Duration, p4Color)

        abilityCooldown = true
        wait(15)
        statusLabel.Text = "SPEC STATUS: <font color=\"rgb(255, 0, 0)\">0</font>"

        countdownRunning = true
        for countdown = 120, 0, -1 do
            statusLabel.Text = "SPEC STATUS: <font color=\"rgb(255, 0, 0)\">" .. countdown .. "</font>"
            wait(1)
        end

        statusLabel.Text = "SPEC STATUS: <font color=\"rgb(0, 255, 0)\">READY</font>"

        wait(15)
        abilityCooldown = false
        countdownRunning = false
    end
end)

if Fluent and SaveManager and InterfaceManager then
    local Window = Fluent:CreateWindow({
        Title = "Beyond Volleyball League",
        SubTitle = "by Sushi Hub",
        TabWidth = 160,
        Size = UDim2.fromOffset(580, 460),
        Acrylic = false,
        Theme = "Dark",
        MinimizeKey = Enum.KeyCode.LeftControl
    })

    local Tabs = {
        Specs = Window:AddTab({ Title = "Specs 100% Unc", Icon = "" }),
		Player = Window:AddTab({ Title = "Player", Icon = "" }),
		Others = Window:AddTab({ Title = "Others", Icon = "" }),
    }


        local InterfaceSection = Tabs.Others:AddSection("Pickups")

        Tabs.Others:AddButton({
            Title = "Pickups (Red)",
            Description = "",
            Callback = function()
                Window:Dialog({
                    Title = "Pickups (Red)",
                    Content = "",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()
                                local function sendPickup(color, number)
                                    game:GetService("ReplicatedStorage").Misc.Pickups.Remotes.PickupsManager:FireServer(color, number)
                                end
                                
                                for i = 1, 6 do
                                    sendPickup("Red", i)
                                print("Join Red")
                                end
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                            
                            end
                        }
                    }
                })
            end
        })
    
        

        Tabs.Others:AddButton({
            Title = "Pickups (Blue)",
            Description = "",
            Callback = function()
                Window:Dialog({
                    Title = "Pickups (Blue)",
                    Content = "",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()
                                local function sendPickup(color, number)
                                    game:GetService("ReplicatedStorage").Misc.Pickups.Remotes.PickupsManager:FireServer(color, number)
                                end
                                
                                for i = 1, 6 do
                                    sendPickup("Blue", i)
                                print("Join Blue")
                                end
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                            
                            end
                        }
                    }
                })
            end
        })
    
    local Options = Fluent.Options

    local connection 

    do
        Fluent:Notify({
            Title = "Notification",
            Content = "This is a notification From Sushi Hub",
            SubContent = "Sushi Hub Best Script", -- Optional
            Duration = 5 -- Set to nil to make the notification not disappear
        })

        local InterfaceSection = Tabs.Specs:AddSection("Outside")

        Tabs.Specs:AddButton({
            Title = "Tenma Udai (Outside Hitter)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "Tenma Udai",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

                                            })
            end
        })

        Tabs.Specs:AddButton({
            Title = "Asahi Azumane (Outside Hitter)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "Asahi Azumane",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

-- à¹‚à¸„à¹‰à¸”à¸«à¸¥à¸±à¸à¸‚à¸­à¸‡ executor
local v0_2_ = game
local v0_1_ = v0_2_.Players
local v0_0_ = v0_1_.LocalPlayer

-- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†
local maxPower = 16

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI


                                local player = game.Players.LocalPlayer
                                _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.MaxStam = 15 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.Height = "6'3" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
_G.Spec = "Asahi" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
_G.Trait = "Asahi" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SubTrait = "Asahi's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SpecActivated = true

loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                                
    end
                        }
                    }
                })
            end
        })

        Tabs.Specs:AddButton({
            Title = "Aran Ojiro (Outside Hitter)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "Aran Ojiro",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

                            -- à¹‚à¸„à¹‰à¸”à¸«à¸¥à¸±à¸à¸‚à¸­à¸‡ executor
local v0_2_ = game
local v0_1_ = v0_2_.Players
local v0_0_ = v0_1_.LocalPlayer

-- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†
local maxPower = 16

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI


                                local player = game.Players.LocalPlayer
                                _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.MaxStam = 15 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.Height = "6'2" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
_G.Spec = "Aran" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
_G.Trait = "Aran" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SubTrait = "Aran's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SpecActivated = true

loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                              
    end
                        }
                    }
                })
            end
        })

        Tabs.Specs:AddButton({
            Title = "Wakatsu KiryÅ« (Outside Hitter)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "Wakatsu KiryÅ«",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

-- à¹‚à¸„à¹‰à¸”à¸«à¸¥à¸±à¸à¸‚à¸­à¸‡ executor
local v0_2_ = game
local v0_1_ = v0_2_.Players
local v0_0_ = v0_1_.LocalPlayer

-- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†
local maxPower = 16.7

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI


                                local player = game.Players.LocalPlayer
                                _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.MaxStam = 15 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.Height = "6'3" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
_G.Spec = "Kiryuu" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
_G.Trait = "Kiryuu" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SubTrait = "Kiryuu's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SpecActivated = true

loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                                
    end
                        }
                    }
                })
            end
        })

        Tabs.Specs:AddButton({
            Title = "Kiyoomi Sakusa (Outside Hitter)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "Kiyoomi Sakusa",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

                                            })
            end
        })

        Tabs.Specs:AddButton({
            Title = "KÅtarÅ Bokuto (Outside Hitter)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "KÅtarÅ Bokuto",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

-- à¹‚à¸„à¹‰à¸”à¸«à¸¥à¸±à¸à¸‚à¸­à¸‡ executor
local v0_2_ = game
local v0_1_ = v0_2_.Players
local v0_0_ = v0_1_.LocalPlayer

-- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†
local maxPower = 16

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI


                                local player = game.Players.LocalPlayer
                                _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.MaxStam = 15 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.Height = "6'3" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
_G.Spec = "Bokuto" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
_G.Trait = "Bokuto" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SubTrait = "Bokuto's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SpecActivated = true

loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                               
    end
                        }
                    }
                })
            end
        })

        local InterfaceSection = Tabs.Specs:AddSection("Middle")

        Tabs.Specs:AddButton({
            Title = "SachirÅ Hirugami (Middle Blocker)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "SachirÅ Hirugami",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

                            local maxPower = 15

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI


                                local player = game.Players.LocalPlayer
                                _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.MaxStam = 15 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.Height = "6'4" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
_G.Spec = "Aone" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
_G.Trait = "Aone" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SubTrait = "Aone's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SpecActivated = true

loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                              
    end
                        }
                    }
                })
            end
        })

        Tabs.Specs:AddButton({
            Title = "Satori TendÅ (Middle Blocker)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "Satori TendÅ",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

                            multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                               
    end
                        }
                    }
                })
            end
        })

        Tabs.Specs:AddButton({
            Title = "Atsumu Miya (Setter)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "Atsumu Miya",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

-- à¹‚à¸„à¹‰à¸”à¸«à¸¥à¸±à¸à¸‚à¸­à¸‡ executor
local v0_2_ = game
local v0_1_ = v0_2_.Players
local v0_0_ = v0_1_.LocalPlayer

-- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†
local maxPower = 16.5

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI

                Window:Dialog({
                    Title = "Kanji Koganegawa",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

-- à¹‚à¸„à¹‰à¸”à¸«à¸¥à¸±à¸à¸‚à¸­à¸‡ executor
local v0_2_ = game
local v0_1_ = v0_2_.Players
local v0_0_ = v0_1_.LocalPlayer

-- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†
local maxPower = 16

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI

                            
                                local player = game.Players.LocalPlayer
                                _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.MaxStam = 15 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.Height = "6'5" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
_G.Spec = "Koganegawa" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
_G.Trait = "Koganegawa" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SubTrait = "Koganegawa's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SpecActivated = true

loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                                
    end
                        }
                    }
                })
            end
        })

        Tabs.Specs:AddButton({
            Title = "Kenma Kozume (Setter)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "Kenma Kozume",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

                            
-- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†
local maxPower = 16

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI


                                local player = game.Players.LocalPlayer
                                _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.MaxStam = 15 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.Height = "6'8" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
_G.Spec = "Gao" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
_G.Trait = "Gao" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SubTrait = "Gao's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SpecActivated = true

loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                                
    end
                        }
                    }
                })
            end
        })

        Tabs.Specs:AddButton({
            Title = "KentarÅ KyÅtani (Opposite Hitter)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "KentarÅ KyÅtani",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

                            -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†
local maxPower = 15

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI


                                local player = game.Players.LocalPlayer
                                    _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
    _G.MaxStam = 20
    _G.Height = "5'11" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
    _G.Spec = "Motoya" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
    _G.Trait = "Motoya" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
    _G.SubTrait = "Motoya's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
    _G.SpecActivated = true
    
    loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()
    
                                    -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                    player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                    player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                            
                           end
                        }
                    }
                })
            end
        })

        Tabs.Specs:AddButton({
            Title = "Yaku Morisuke (Libero)",
            Description = "Haikyuu",
            Callback = function()
                Window:Dialog({
                    Title = "Yaku Morisuke",
                    Content = "Do you want to use spec?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()

                            local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI


                            local player = game.Players.LocalPlayer
                                _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.MaxStam = 20
_G.Height = "5'4" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
_G.Spec = "Nishinoya" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
_G.Trait = "Nishinoya" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SubTrait = "Nishinoya's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SpecActivated = true

loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                        end
                    },
                    {
                        Title = "Cancel",
                        Callback = function()
                            
                       end
                    }
                }
            })
        end
    })

    local InterfaceSection = Tabs.Specs:AddSection("Misc")

    Tabs.Specs:AddButton({
        Title = "Yamaguchi",
        Description = "Haikyuu",
        Callback = function()
            Window:Dialog({
                Title = "Yamaguchi",
                Content = "Do you want to use spec?",
                Buttons = {
                    {
                        Title = "Confirm",
                        Callback = function()

-- à¹‚à¸„à¹‰à¸”à¸«à¸¥à¸±à¸à¸‚à¸­à¸‡ executor
local v0_2_ = game
local v0_1_ = v0_2_.Players
local v0_0_ = v0_1_.LocalPlayer

-- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†
local maxPower = 15

-- à¹ƒà¸Šà¹‰ EffectStorage à¸ˆà¸²à¸ ReplicatedStorage
local v0_6_ = game.ReplicatedStorage.EffectStorage
local v0_4_ = require(v0_6_)

-- à¸–à¹‰à¸²à¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹ƒà¸«à¹‰à¸žà¸¥à¸±à¸‡à¹€à¸›à¹‡à¸™ 16 à¹€à¸—à¹ˆà¸²à¸™à¸±à¹‰à¸™
local v0_5_ = v0_4_.getData()
v0_5_.MaxPower = maxPower  -- à¸•à¸±à¹‰à¸‡à¸„à¹ˆà¸² MaxPower à¹€à¸›à¹‡à¸™ 16 à¸•à¸£à¸‡ à¹†

-- à¸«à¸²à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™ Character
local v0_6_ = v0_0_.Character
local v0_8_ = "Power"
v0_6_ = v0_6_:WaitForChild(v0_8_)

-- à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¸žà¸¥à¸±à¸‡à¹ƒà¸™à¸£à¸¹à¸›à¹à¸šà¸š maxPower
local powerValue = v0_6_.Value
local powerText = powerValue .. "/" .. maxPower

-- à¹à¸ªà¸”à¸‡à¸œà¸¥à¸—à¸µà¹ˆ TextLabel (à¸–à¹‰à¸²à¹ƒà¸Šà¹‰ executor à¸—à¸µà¹ˆà¸£à¸­à¸‡à¸£à¸±à¸š UI, à¹à¸•à¹ˆà¹ƒà¸™à¸à¸£à¸“à¸µà¸™à¸µà¹‰à¸­à¸²à¸ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£à¹à¸„à¹ˆà¸žà¸¥à¸±à¸‡ 16)
print(powerText)  -- à¹€à¸£à¸²à¸ˆà¸°à¹à¸ªà¸”à¸‡à¸„à¹ˆà¸²à¹ƒà¸™ console à¹à¸—à¸™ UI


                            local player = game.Players.LocalPlayer
                                _G.Jump = 5 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.MaxStam = 15 -- à¸«à¹‰à¸²à¸¡à¸›à¸£à¸±à¸š
_G.Height = "5'11" -- à¹ƒà¸ªà¹ˆà¸ªà¹ˆà¸§à¸™à¸ªà¸¹à¸‡à¸•à¸±à¸§à¹€à¸­à¸‡
_G.Spec = "Yamaguchi" -- à¹ƒà¸ªà¹ˆ Spec à¸—à¸µà¹ˆà¸•à¹‰à¸­à¸‡à¸à¸²à¸£
_G.Trait = "Yamaguchi" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SubTrait = "Yamaguchi's Sub" -- à¹ƒà¸ªà¹ˆ Spec à¸­à¸±à¸™à¹€à¸”à¸µà¸¢à¸§à¸à¸±à¸™
_G.SpecActivated = true

loadstring(game:HttpGet("https://raw.githubusercontent.com/keirahela/bvl-multipurpose/main/script.lua", true))()

                                -- à¹€à¸›à¸´à¸”à¹ƒà¸Šà¹‰à¸‡à¸²à¸™ GUI 
                                player.PlayerGui.PowerStam.Main.SpecStatus.Active = true
                                player.PlayerGui.PowerStam.Main.SpecStatus.Visible = true
                        end
                    },
                    {
                        Title = "Cancel",
                        Callback = function()
                            
                       end
                    }
                }
            })
        end
    })

    Tabs.Specs:AddButton({
        Title = "Admin",
        Description = "Beyond Volleyball League",
        Callback = function()
            Window:Dialog({
                Title = "Admin",
                Content = "Do you want to use spec?",
                Buttons = {
                    {
                        Title = "Confirm",
                        Callback = function()

                        
    Tabs.Others:AddButton({
        Title = "Hair (15 Kash)",
        Description = "",
        Callback = function()
            Window:Dialog({
                Title = "Hair",
                Content = "Spin Hair ?",
                Buttons = {
                    {
                        Title = "Confirm",
                        Callback = function()
                            game:GetService("ReplicatedStorage").Remotes.RerollRemotes.Reroll.Hair:FireServer()
                        end
                    },
                    {
                        Title = "Cancel",
                        Callback = function()
                            
                        end
                    }
                }
            })
        end
    })

    Tabs.Others:AddButton({
        Title = "SubTrait (25 Kash)",
        Description = "",
        Callback = function()
            Window:Dialog({
                Title = "SubTrait",
                Content = "Spin SubTrait ?",
                Buttons = {
                    {
                        Title = "Confirm",
                        Callback = function()
                            game:GetService("ReplicatedStorage").Remotes.RerollRemotes.Reroll.SubTrait:FireServer()
                        end
                    },
                    {
                        Title = "Cancel",
                        Callback = function()
                            
                        end
                    }
                }
            })
        end
    })

    Tabs.Others:AddButton({
        Title = "Trait (50 Kash)",
        Description = "",
        Callback = function()
            Window:Dialog({
                Title = "Trait",
                Content = "Spin Trait ?",
                Buttons = {
                    {
                        Title = "Confirm",
                        Callback = function()
                            game:GetService("ReplicatedStorage").Remotes.RerollRemotes.Reroll.Trait:FireServer()
                        end
                    },
                    {
                        Title = "Cancel",
                        Callback = function()
                            
                        end
                    }
                }
            })
        end
    })


Tabs.Player:AddSlider("JumpPower", {
    Title = "JumpPower", 
    Description = "Change the jump power", 
    Default = 9, -- Define um valor padrÃ£o para o slider
    Min = 1, 
    Max = 100, 
    Rounding = 1,
    Callback = function(value)
        local player = game.Players.LocalPlayer

        game.Workspace[player.Name].Humanoid.JumpHeight = value

(7533581)while(191+-0x7a)>=h do o-= o if not e[l[K]]then d=d+n;else d=l[O];end;break;end while(o)/((0x80df9/195))==2783 do o=(3696330)while h>(0x102-188)do o-= o local o=l[r];local d=e[l[M]];e[o+1]=d;e[o]=d[l[u]];break end while(o)/((0xb86-1489))==2530 do e[l[r]]=(l[w]~=0);break end;break;end break;end break;end break;end break;end while 3153==(o)/((0x3d448/104))do o=(2278276)while(-0x18+107)>=h do o-= o o=(6821500)while h<=(224-(0x893d/239))do o-= o o=(1413765)while h<=(158+-0x54)do o-= o o=(12588238)while h<=(-0x15+93)do o-= o local l=l[r]e[l]=e[l](e[l+n])break;end while(o)/((0x1cae-3689))==3446 do o=(5209677)while h>(0x2480/128)do o-= o i[l[M]]=e[l[r]];d=d+b;l=k[d];e[l[a]]={};d=d+b;l=k[d];e[l[x]]={};d=d+b;l=k[d];i[l[B]]=e[l[x]];d=d+b;l=k[d];e[l[P]]=i[l[F]];d=d+b;l=k[d];if(e[l[H]]~=l[U])then d=d+n;else d=l[p];end;break end while 1949==(o)/((5395-0xaa2))do e[l[r]]=e[l[M]]-e[l[L]];break end;break;end break;end while(o)/((458+-0x69))==4005 do o=(6103064)while(0x79+-46)>=h do o-= o e[l[P]]=e[l[p]][e[l[S]]];break;end while 1784==(o)/((0x1b20-3523))do o=(11766148)while h>(228/0x3)do o-= o local l=l[K]local d,o=D(e[l](e[l+n]))m=o+l-b local o=0;for l=l,m do o=o+b;e[l]=d[o];end;break end while(o)/((-0x64+4059))==2972 do e[l[H]]=_[l[M]];d=d+b;l=k[d];e[l[a]]=#e[l[w]];d=d+b;l=k[d];_[l[p]]=e[l[a]];d=d+b;l=k[d];e[l[P]]=_[l[F]];d=d+b;l=k[d];e[l[a]]=#e[l[B]];d=d+b;l=k[d];_[l[p]]=e[l[P]];d=d+b;l=k[d];do return end;break end;break;end break;end break;end while 3500==(o)/((3987-0x7f6))do o=(6542721)while(-24+0x68)>=h do o-= o o=(667584)while(0x2e9e/153)>=h do o-= o e[l[K]]=e[l[p]][e[l[L]]];break;end while(o)/((3016-0x610))==456 do o=(12990180)while h>(189+-0x6e)do o-= o e[l[r]]=_[l[p]];break end while 3297==(o)/((7922-0xf8e))do local n;local f,P;local h;local o;i[l[O]]=e[l[x]];d=d+b;l=k[d];e[l[a]]=i[l[M]];d=d+b;l=k[d];e[l[x]]=i[l[F]];d=d+b;l=k[d];o=l[r];h=e[l[p]];e[o+1]=h;e[o]=h[l[S]];d=d+b;l=k[d];e[l[a]]=l[M];d=d+b;l=k[d];o=l[K]f,P=D(e[o](c(e,o+1,l[F])))m=P+o-1 n=0;for l=o,m do n=n+b;e[l]=f[n];end;d=d+b;l=k[d];o=l[a]e[o]=e[o](c(e,o+b,m))d=d+b;l=k[d];o=l[x]e[o]=e[o]()d=d+b;l=k[d];e[l[K]]=i[l[p]];d=d+b;l=k[d];o=l[x];h=e[l[M]];e[o+1]=h;e[o]=h[l[S]];break end;break;end break;end while 1917==(o)/((300344/0x58))do o=(3334386)while h<=(0xd2-129)do o-= o local K;local h;local m;local o;e[l[r]]=i[l[w]];d=d+b;l=k[d];e[l[P]]=e[l[M]][l[U]];d=d+b;l=k[d];o=l[x];m=e[l[O]];e[o+1]=m;e[o]=m[l[t]];d=d+b;l=k[d];e[l[H]]=e[l[O]];d=d+b;l=k[d];e[l[H]]=e[l[p]];d=d+b;l=k[d];o=l[P]e[o]=e[o](c(e,o+b,l[F]))d=d+b;l=k[d];o=l[x];m=e[l[w]];e[o+1]=m;e[o]=m[l[C]];d=d+b;l=k[d];o=l[x]e[o]=e[o](e[o+n])d=d+b;l=k[d];h={e,l};h[n][h[f][a]]=h[b][h[f][S]]+h[n][h[f][p]];d=d+b;l=k[d];e[l[a]]=e[l[p]]%l[U];d=d+b;l=k[d];o=l[r]e[o]=e[o](e[o+n])d=d+b;l=k[d];m=l[B];K=e[m]for l=m+1,l[t]do K=K..e[l];end;e[l[P]]=K;d=d+b;l=k[d];h={e,l};h[n][h[f][x]]=h[b][h[f][L]]+h[n][h[f][p]];d=d+b;l=k[d];e[l[a]]=e[l[O]]%l[U];break;end while 2659==(o)/((0x21ad4/110))do o=(1980800)while(249-0xa7)<h do o-= o e[l[x]]=e[l[F]][l[t]];break end while(o)/((-17+0xc28))==640 do local h=j[l[F]];local b;local o={};b=V({},{__index=function(e,l)local l=o[l];return l[1][l[2]];end,__newindex=function(d,l,e)local l=o[l]l[1][l[2]]=e;end;});for b=1,l[U]do d=d+n;local l=k[d];if l[(113+-0x70)]==9 then o[b-1]={e,l[O]};else o[b-1]={_,l[M]};end;s[#s+1]=o;end;e[l[a]]=N(h,b,i);break end;break;end break;end break;end break;end while(o)/((0x1f8f8/226))==3983 do o=(135162)while(0x24da/106)>=h do o-= o o=(4340160)while(-0x55+(0x1ae-259))>=h do o-= o o=(13192014)while h<=(0x126-210)do o-= o e[l[P]][e[l[F]]]=e[l[u]];break;end while(o)/((0xfde+-104))==3333 do o=(11930146)while h>(0x107-178)do o-= o local l=l[P]e[l]=e[l](c(e,l+b,m))break end while(o)/(((6350-0xc8d)+-0x1f))==3841 do e[l[r]]=_[l[p]];break end;break;end break;end while(o)/((0x9d5-1284))==3520 do o=(14574)while(0x3765/163)>=h do o-= o e[l[x]]=#e[l[O]];break;end while(o)/((0x72-(175+-0x67)))==347 do o=(3414080)while(173+-0x55)<h do o-= o do return e[l[P]]end break end while 1880==(o)/((-0x21+1849))do local o;o=l[x]e[o]=e[o](c(e,o+b,l[F]))d=d+b;l=k[d];for l=l[H],l[F]do e[l]=nil;end;d=d+b;l=k[d];e[l[r]]=i[l[F]];d=d+b;l=k[d];o=l[a]e[o]=e[o]()d=d+b;l=k[d];e[l[a]][l[O]]=l[U];d=d+b;l=k[d];e[l[H]]=i[l[F]];d=d+b;l=k[d];e[l[K]]=i[l[w]];d=d+b;l=k[d];e[l[x]]=l[O];break end;break;end break;end break;end while 54==(o)/((0x23716/58))do o=(1154748)while(0x137-(37011/0xa9))>=h do o-= o o=(2552541)while(0x104-170)>=h do o-= o e[l[P]]=e[l[M]]%l[L];break;end while(o)/((-91+0x382))==3163 do o=(2142100)while(-53+0x90)<h do o-= o local l=l[r];m=l+g-1;for o=l,m do local l=v[o-l];e[o]=l;end;break end while(o)/(((-0x4b+0)+0x2fe))==3100 do if(e[l[a]]==e[l[C]])then d=d+n;else d=l[F];end;break end;break;end break;end while 932==(o)/((0x3e502/206))do o=(1097283)while(254-0xa1)>=h do o-= o local l=l[x]e[l](e[l+n])break;end while(o)/((0x992+-17))==451 do o=(5996835)while(-0x58+182)<h do o-= o e[l[a]]=i[l[B]];break end while(o)/((-49+0xbf8))==1989 do if(e[l[K]]~=l[L])then d=d+n;else d=l[w];end;break end;break;end break;end break;end break;end break;end break;end d+= n end;end);end;return N(G(),{},Y())()end)_msec({[(323-0xb2)]='\115\116'..(function(l)return(l and'(281-(0x181-204))')or'\114\105'or'\120\58'end)((0x2df/147)==(1350/0xe1))..'\110g',[(0x216e7/179)]='\108\100'..(function(l)return(l and'(-45+0x91)')or'\101\120'or'\119\111'end)((0x27-34)==(0x36/9))..'\112',[(0x20e-271)]=(function(l)return(l and'(17500/0xaf)')and'\98\121'or'\100\120'end)((335/0x43)==(0x7a-117))..'\116\101',[(362+-0x12)]='\99'..(function(l)return(l and'(-105+0xcd)')and'\90\19\157'or'\104\97'end)((-54+0x3b)==(486/0xa2))..'\114',[(-87+(744+-0x63))]='\116\97'..(function(l)return(l and'(-0x48+172)')and'\64\113'or'\98\108'end)((55+-0x31)==(0x451/221))..'\101',[(0x38d-469)]=(function(l)return(l and'(263-0xa3)')or'\115\117'or'\78\107'end)((0x252/198)==(0x47b/37))..'\98',[(916+-0x60)]='\99\111'..(function(l)return(l and'(0xec-136)')and'\110\99'or'\110\105\103\97'end)((0x51+-50)==(-0x4a+105))..'\97\116',[(-104+0x31a)]=(function(l,o)return(l and'(0x1c84/73)')and'\48\159\158\188\10'or'\109\97'end)((92-0x57)==(396/0x42))..'\116\104',[(175560/0x85)]=(function(l,o)return((121+-0x74)==(28-(0xb22/114))and'\48'..'\195'or l..((not'\20\95\69'and'\90'..'\180'or o)))or'\199\203\95'end),[((1158+-0x48)+-120)]='\105\110'..(function(l,o)return(l and'(0x6a4/17)')and'\90\115\138\115\15'or'\115\101'end)((0x276/126)==((-99+0x598)/0x2b))..'\114\116',[(0x9362/35)]='\117\110'..(function(l,o)return(l and'(0x1c20/72)')or'\112\97'or'\20\38\154'end)((93-0x58)==(0x6d-78))..'\99\107',[(0x468/1)]='\115\101'..(function(l)return(l and'(0xf8-148)')and'\110\112\99\104'or'\108\101'end)((87-0x52)==(79-0x30))..'\99\116',[(0xa21-1343)]='\116\111\110'..(function(l,o)return(l and'(4200/0x2a)')and'\117\109\98'or'\100\97\120\122'end)((0x81-124)==(0x5a-85))..'\101\114'},{[(7004/0x67)]=((getfenv))},((getfenv))()) end)()

                                print("Anti Chest")
    end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()

                            end
                        }
                    }
                })
            end
        })

        Tabs.Others:AddButton({
            Title = "Anti AFK",
            Description = "",
            Callback = function()
                Window:Dialog({
                    Title = "Anti AFK",
                    Content = "Do u want AFK ?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()
                            -- Anti AFK Script
local Players = game:GetService("Players")
local VirtualUser = game:GetService("VirtualUser")

-- Event listener for when a player is about to be kicked for idling
Players.LocalPlayer.Idled:Connect(function()
    VirtualUser:CaptureController()
    VirtualUser:ClickButton2(Vector2.new()) -- Simulates a right mouse button click
end)
print("AFK")
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()
                                
                            end
                        }
                    }
                })
            end
        })

        Tabs.Others:AddButton({
            Title = "Rejoin",
            Description = "",
            Callback = function()
                Window:Dialog({
                    Title = "Rejoin",
                    Content = "Do u want Rejoin ?",
                    Buttons = {
                        {
                            Title = "Confirm",
                            Callback = function()
                                local ts = game:GetService("TeleportService")

local p = game:GetService("Players").LocalPlayer



ts:TeleportToPlaceInstance(game.PlaceId, game.JobId, p)
                                 Print("Rejoin")
                            end
                        },
                        {
                            Title = "Cancel",
                            Callback = function()

                            end
                        }
                    }
                })
            end
        })


    Tabs.Others:AddButton({
        Title = "HitFeed",
        Description = "Show HitFeed",
        Callback = function()
            Window:Dialog({
                Title = "HitFeed",
                Content = "Do u want HitFeed ?",
                Buttons = {
                    {
                        Title = "Confirm",
                        Callback = function()
                            game:GetService("Players").LocalPlayer.PlayerGui["Other GUis"]["Hit Feed"].Visible = true
                        end
                    },
                    {
                        Title = "Cancel",
                        Callback = function()
                            
                        end
                    }
                }
            })
        end
    })

local AntiSection = Tabs.Others:AddSection("Anti")



AntiSection:AddButton({
	Title = "LockCourt",
	Description = "Let the court unlocked",
	Callback = function()
    
        game.Workspace.LockCourt:Destroy()

    
	end
})

AntiSection:AddButton({
	Title = "Serve LF",
	Description = "Remove the Serve LF",
	Callback = function()
    
        game.Workspace.ServeLF.Size = Vector3.new(0.001, 1, 0.001)

    
	end
})

AntiSection:AddButton({
	Title = "Ceiling",
	Description = "Remove the Max Jump Limit",
	Callback = function()
    
        game.Workspace.Ceiling:Destroy()

    
	end
})



    local Tabs = {
        Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
    }

        -- Addons:
        -- SaveManager (Allows you to have a configuration system)
        -- InterfaceManager (Allows you to have a interface managment system)

-- Hand the library over to our managers
        SaveManager:SetLibrary(Fluent)
        InterfaceManager:SetLibrary(Fluent)

        -- Ignore keys that are used by ThemeManager.
        -- (we dont want configs to save themes, do we?)
        SaveManager:IgnoreThemeSettings()

        -- You can add indexes of elements the save manager should ignore
        SaveManager:SetIgnoreIndexes({})

        -- use case for doing it this way:
        -- a script hub could have themes in a global folder
        -- and game configs in a separate folder per game
        InterfaceManager:SetFolder("FluentScriptHub")
        SaveManager:SetFolder("FluentScriptHub/specific-game")

        InterfaceManager:BuildInterfaceSection(Tabs.Settings)
        SaveManager:BuildConfigSection(Tabs.Settings)

        Window:SelectTab(1)

        Fluent:Notify({
            Title = "Sushi Hub",
            Content = "Sushi Hub has been loaded.",
            Duration = 8
        })

     

        SaveManager:LoadAutoloadConfig()
    end
else
    warn("Failed to load one or more necessary scripts.")
end
else
  
local function kickPlayer()
  
    local player = game.Players.LocalPlayer
    if player then
      
        player:Kick("Can Use Only Beyond Volleyball League. !")
    else
        
    end
end

kickPlayer()

end
