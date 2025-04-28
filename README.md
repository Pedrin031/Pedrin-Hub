local Library = loadstring(Game:HttpGet("https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/wizard"))()      

local Window = Library:NewWindow("Pedrin")

local Tab = Window:NewSection("Options")

-- Botão para copiar o link do Discord
Tab:CreateButton("Copiar Link do Discord", function()
    setclipboard("https://discord.gg/jfKVrrMx")
end)

Tab:CreateTextbox("TextBox", function(text)
    print(text)
end)

Tab:CreateDropdown("DropDown", {"Hello", "World", "Hi World"}, 2, function(text)
    print(text)
end)

Tab:CreateSlider("Slider", 0, 100, 15, false, function(value)
    print(value)
end)

Tab:CreateColorPicker("Picker", Color3.fromRGB(255, 255, 255), function(color)
    print(color)
end)

Tab:CreateToggle("Toggle", function(state)
    print(state)
end)
