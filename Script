-- Gui to Lua
-- Version: 3.2

-- Instances:

local FlyScript = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local TextButton = Instance.new("TextButton")
local UICorner_2 = Instance.new("UICorner")
local IsOn = Instance.new("TextButton")
local UICorner_3 = Instance.new("UICorner")
local TextButton2 = Instance.new("TextBox")
local UICorner_4 = Instance.new("UICorner")

--Properties:

FlyScript.Name = "FlyScript"
FlyScript.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

Frame.Parent = FlyScript
Frame.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
Frame.BackgroundTransparency = 1.000
Frame.Position = UDim2.new(0, 0, 0.684542596, 0)
Frame.Selectable = true
Frame.Size = UDim2.new(0.296442688, 0, 0.315457404, 0)

UICorner.CornerRadius = UDim.new(0.0199999996, 0)
UICorner.Parent = Frame

TextButton.Parent = Frame
TextButton.BackgroundColor3 = Color3.fromRGB(120, 120, 120)
TextButton.BorderSizePixel = 0
TextButton.Position = UDim2.new(0.246271417, 0, 0.182839051, 0)
TextButton.Size = UDim2.new(0.393333346, 0, 0.25, 0)
TextButton.Font = Enum.Font.FredokaOne
TextButton.Text = "Fly: "
TextButton.TextColor3 = Color3.fromRGB(255, 255, 255)
TextButton.TextScaled = true
TextButton.TextSize = 14.000
TextButton.TextWrapped = true
TextButton.TextXAlignment = Enum.TextXAlignment.Left

UICorner_2.CornerRadius = UDim.new(0, 30)
UICorner_2.Parent = TextButton

IsOn.Name = "IsOn"
IsOn.Parent = Frame
IsOn.BackgroundColor3 = Color3.fromRGB(120, 120, 120)
IsOn.BackgroundTransparency = 1.000
IsOn.BorderSizePixel = 0
IsOn.Position = UDim2.new(0.45960474, 0, 0.182839051, 0)
IsOn.Size = UDim2.new(0.180000007, 0, 0.25, 0)
IsOn.Font = Enum.Font.FredokaOne
IsOn.Text = "Off"
IsOn.TextColor3 = Color3.fromRGB(255, 0, 0)
IsOn.TextScaled = true
IsOn.TextSize = 14.000
IsOn.TextWrapped = true

UICorner_3.CornerRadius = UDim.new(0, 30)
UICorner_3.Parent = IsOn

TextButton2.Name = "TextButton2"
TextButton2.Parent = Frame
TextButton2.BackgroundColor3 = Color3.fromRGB(120, 120, 120)
TextButton2.Position = UDim2.new(0.259604752, 0, 0.532839, 0)
TextButton2.Size = UDim2.new(0.379999995, 0, 0.25, 0)
TextButton2.Font = Enum.Font.FredokaOne
TextButton2.PlaceholderColor3 = Color3.fromRGB(0, 0, 0)
TextButton2.PlaceholderText = "Speed"
TextButton2.Text = ""
TextButton2.TextScaled = true
TextButton2.TextWrapped = true

UICorner_4.CornerRadius = UDim.new(0, 30)
UICorner_4.Parent = TextButton2

-- Scripts:

local function EURQXKU_fake_script() -- Frame.Drag script 
	local script = Instance.new('LocalScript', Frame)

	--Credits go to whoever made this script.
	--put this into frame of your GUI
	
	local UIS = game:GetService("UserInputService")
	function drag (Frame)
		dragToggle = nil
		dragSpeed = 0.23 --change drag speed here (up to 1 down to 0)
		dragInput = nil
		dragStart = nil
		dragPos = nil
		function updateInput(input)
			Delta = input.Position - dragStart
			Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + Delta.X, startPos.Y.Scale, startPos.Y.Offset + Delta.Y)
			game:GetService("TweenService"):Create(Frame, TweenInfo.new(0.25), {Position = Position}):Play()
		end
		Frame.InputBegan:Connect(function(input)
			if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) and UIS:GetFocusedTextBox() == nil then
				dragToggle = true
				dragStart = input.Position
				startPos = Frame.Position
				input.Changed:Connect(function()
					if input.UserInputState == Enum.UserInputState.End then
						dragToggle = false
					end
				end)
			end
		end)
		Frame.InputChanged:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
				dragInput = input
			end
		end)
		game:GetService("UserInputService").InputChanged:Connect(function(input)
			if input == dragInput and dragToggle then
				updateInput(input)
			end
		end)
	end
	drag(script.Parent)
	
end
coroutine.wrap(EURQXKU_fake_script)()
local function KHKNO_fake_script() -- FlyScript.FlyManager 
	local script = Instance.new('LocalScript', FlyScript)

	
	
	
	local Key = "f" -- Lowercase Letter
	
	
	
	
	
	
	
	
	
	
	
	local Player = game.Players.LocalPlayer
	repeat wait() until Player.Character and Player.Character:FindFirstChild('Humanoid')
	local Mouse = Player:GetMouse()
	local IsFlying = false
	local flyv
	local flyg
	local IsRunning = false
	local f = 0
	local Speed = 50
	local LastSpeed = Speed
	local maxspeed = 100
	local wdown = false
	local sdown = false
	Mouse.KeyDown:Connect(function(key)
		if key:lower() == Key then
			if IsFlying then
				IsFlying = false
			    flyv:Destroy()
				flyg:Destroy()
				script.Parent.Frame.IsOn.Text = "Off"
				script.Parent.Frame.IsOn.TextColor3 = Color3.fromRGB(255,0,0)
				Player.Character:WaitForChild('Humanoid').PlatformStand = false
			else
				IsFlying = true
				 flyv = Instance.new("BodyVelocity")
				
				flyv.Parent = Player.Character:FindFirstChild('Torso') or Player.Character:FindFirstChild('UpperTorso')
				flyv.MaxForce = Vector3.new(math.huge,math.huge,math.huge)
				
				 flyg = Instance.new("BodyGyro")
				flyg.Parent = Player.Character:FindFirstChild('Torso') or Player.Character:FindFirstChild('UpperTorso')
				flyg.MaxTorque = Vector3.new(9e9,9e9,9e9)
				flyg.P = 1000
				flyg.D = 50
				script.Parent.Frame.IsOn.Text = "On"
				script.Parent.Frame.IsOn.TextColor3 = Color3.fromRGB(0,255,0)
				Player.Character:WaitForChild('Humanoid').PlatformStand = true
			end
		end
	end)
	script.Parent.Frame.TextButton.MouseButton1Click:Connect(function()
		
			if IsFlying then
				IsFlying = false
				flyv:Destroy()
				flyg:Destroy()
			    script.Parent.Frame.IsOn.Text = "Off"
			    script.Parent.Frame.IsOn.TextColor3 = Color3.fromRGB(255,0,0)
				Player.Character:WaitForChild('Humanoid').PlatformStand = false
			else
				IsFlying = true
				flyv = Instance.new("BodyVelocity")
	
			flyv.Parent = Player.Character:FindFirstChild('Torso') or Player.Character:FindFirstChild('UpperTorso')
				flyv.MaxForce = Vector3.new(math.huge,math.huge,math.huge)
	
				flyg = Instance.new("BodyGyro")
			flyg.Parent = Player.Character:FindFirstChild('Torso') or Player.Character:FindFirstChild('UpperTorso')
				flyg.MaxTorque = Vector3.new(9e9,9e9,9e9)
				flyg.P = 1000
				flyg.D = 50
			script.Parent.Frame.IsOn.Text = "On"
			script.Parent.Frame.IsOn.TextColor3 = Color3.fromRGB(0,255,0)
			Player.Character:WaitForChild('Humanoid').PlatformStand = true
			end
	end)
	script.Parent.Frame.TextButton2.FocusLost:Connect(function(Entered)
		if Entered then
			local BeginSpeed = tonumber(script.Parent.Frame.TextButton2.Text)
			if BeginSpeed ~= nil then
				Speed = BeginSpeed
				print(BeginSpeed)
			end
		end	
	end)
	
	
	spawn(function()
		while true do
			wait()
		if IsFlying then
			
				flyg.CFrame = workspace.CurrentCamera.CoordinateFrame * CFrame.Angles(-math.rad((f+0)*50*Speed/maxspeed),0,0) 
					flyv.Velocity = workspace.CurrentCamera.CoordinateFrame.LookVector * Speed
					wait(0.1)
				
				if Speed > maxspeed then
					Speed = maxspeed
					f = 1
				else
					f = 0
				end
					if Speed < 0 then
					Speed = 0
					f = 0
				
				end
			
			end
			if IsRunning then
			Speed = LastSpeed
		else
			if not Speed == 0 then
				LastSpeed = Speed
			end 
			Speed = 0
		end
		end
		
		
	end)
	
	Player.Character.Humanoid.Changed:Connect(function()
		if Player.Character.Humanoid.Health == 0 then
		if IsFlying then
		IsFlying = false
		flyg:Destroy()
		flyv:Destroy()
		end
		end
	end)
	Player.Character.Humanoid.Changed:Connect(function(Prop)
		
			if Player.Character.Humanoid.MoveDirection == Vector3.new(0,0,0) then
				IsRunning = false
			else
				IsRunning = true
			end	
	end)
	
	
	
	
	
	
	
end
coroutine.wrap(KHKNO_fake_script)()
