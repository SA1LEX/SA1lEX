скрипт по праву пренадлежит SA1LEX то есть мне 
мой канал в тг: SA1LEX

local library = loadstring(game:HttpGet("https://pastebin.com/raw/RvJ0qewm", true))() --UI библиотека
local main = library:CreateWindow("GUI BY SA1LEX") 



local Section = main:Section("player_mods") 

local mod = main:Button("x100speed", function() 

  game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 100

end)

local mod2 = main:Button("x26speed", function() 

  game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 26

end)

local mod3 = main:Button("x100Jump", function() 

  game.Players.LocalPlayer.Character.Humanoid.JumpPower = 100

end)

local mod4 = main:Button("x50Jump", function() 

  game.Players.LocalPlayer.Character.Humanoid.JumpPower = 50

  
end)

local Section = main:Section("game_hack") 

local mod5 = main:Button("ESP", function() 

  local color = BrickColor.new(500,0,0)
  local transparency = .10
  
  local Players = game:GetService("Players")
  local function _ESP(c)
    repeat wait() until c.PrimaryPart ~= nil
    for i,p in pairs(c:GetChildren()) do
      if p.ClassName == "Part" or p.ClassName == "MeshPart" then
        if p:FindFirstChild("shit") then p.shit:Destroy() end
        local a = Instance.new("BoxHandleAdornment",p)
        a.Name = "shit"
        a.Size = p.Size
        a.Color = color
        a.Transparency = transparency
        a.AlwaysOnTop = true    
        a.Visible = true    
        a.Adornee = p
        a.ZIndex = true    
  
      end
    end
  end
  local function ESP()
    for i,v in pairs(Players:GetChildren()) do
      if v ~= game.Players.LocalPlayer then
        if v.Character then
          _ESP(v.Character)
        end
        v.CharacterAdded:Connect(function(chr)
          _ESP(chr)
        end)
      end
    end
    Players.PlayerAdded:Connect(function(player)
      player.CharacterAdded:Connect(function(chr)
        _ESP(chr)
      end)  
    end)
  end
  ESP()

  
end)



