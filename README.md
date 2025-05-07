-- GUI simples para adicionar Belly infinito (testes autorizados)

-- Remove GUIs duplicadas
pcall(function() game.CoreGui.BellyGUI:Destroy() end)

-- Criar GUI principal
local ScreenGui = Instance.new("ScreenGui", game.CoreGui)
ScreenGui.Name = "BellyGUI"

local Frame = Instance.new("Frame", ScreenGui)
Frame.Size = UDim2.new(0, 250, 0, 140)
Frame.Position = UDim2.new(0.5, -125, 0.5, -70)
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Frame.BorderSizePixel = 0
Frame.Name = "MainFrame"
Frame.Active = true
Frame.Draggable = true

-- Título
local Title = Instance.new("TextLabel", Frame)
Title.Size = UDim2.new(1, 0, 0, 30)
Title.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Title.Text = "Belly Infinito"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextScaled = true
Title.Font = Enum.Font.SourceSansBold

-- Caixa de texto
local TextBox = Instance.new("TextBox", Frame)
TextBox.PlaceholderText = "Digite o valor de Belly"
TextBox.Size = UDim2.new(0.8, 0, 0, 30)
TextBox.Position = UDim2.new(0.1, 0, 0.4, 0)
TextBox.TextScaled = true
TextBox.Font = Enum.Font.SourceSans
TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextBox.TextColor3 = Color3.fromRGB(0, 0, 0)

-- Botão para aplicar
local Button = Instance.new("TextButton", Frame)
Button.Size = UDim2.new(0.8, 0, 0, 30)
Button.Position = UDim2.new(0.1, 0, 0.7, 0)
Button.Text = "Aplicar Belly"
Button.BackgroundColor3 = Color3.fromRGB(0, 170, 0)
Button.TextColor3 = Color3.fromRGB(255, 255, 255)
Button.Font = Enum.Font.SourceSansBold
Button.TextScaled = true

-- Função para aplicar Belly (editável)
Button.MouseButton1Click:Connect(function()
    local value = tonumber(TextBox.Text)
    if value then
        -- Altere esta parte com base na forma como o jogo lida com o valor de Belly
        -- Exemplo genérico:
        local player = game.Players.LocalPlayer
        if player:FindFirstChild("leaderstats") and player.leaderstats:FindFirstChild("Belly") then
            player.leaderstats.Belly.Value = value
        end
    end
end)
