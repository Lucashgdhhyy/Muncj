ArrayField:Destroy()
warn("muncher master")
local ArrayField = loadstring(game:HttpGet("https://raw.githubusercontent.com/Hosvile/Refinement/main/MC%3AArrayfield%20Library"))()
local Window = ArrayField:CreateWindow({
   Name = "Muncher Master Script",
   LoadingTitle = "By X Azure",
   LoadingSubtitle = "by BaconExility",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Muncher Master Load"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Key",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using ArrayField may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like ArrayField to get the key from
      Actions = {
            [1] = {
                Text = 'Click here to copy the key link <--',
                OnPress = function()
                    print('Pressed')
                end,
                }
            },
      Key = {"Munch"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local Tab = Window:CreateTab("Food", 4483362458) -- Title, Image


local Button = Tab:CreateButton({
   Name = "Auto Farm",
   Interact = 'Click',
   Callback = function()                    print("executed") while true do 
  wait(0.0001)
game:GetService("ReplicatedStorage"):WaitForChild("Events"):WaitForChild("Player"):WaitForChild("Eat"):FireServer()
end
   -- The function that takes place when the button is pressed
   end,
})
