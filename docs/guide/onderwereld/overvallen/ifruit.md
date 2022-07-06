---
description: Put the money in the bag!
---

# 🔫 qb-storerobbery

## Introduction



## Configuration

### General

```lua
Config.minEarn = 100 -- minimum markedbills worth
Config.maxEarn = 450 -- max markedbills worth
Config.RegisterEarnings = math.random(Config.minEarn, Config.maxEarn) -- Randomized earnings
Config.MinimumStoreRobberyPolice = 2 -- minimum police needed to start the robbery
Config.resetTime = (60 * 1000) * 30 -- cooldown between robberies in minutes
Config.tickInterval = 1000 -- the time between register checks
```

### Registers

```lua
Config.Registers = {
    [1] = {
        vector3(-47.24,-1757.65, 29.53), -- register location
        robbed = false, -- dynamically changed, don't edit
        time = 0, -- dynamically changed, don't edit
        safeKey = 1, -- index that references the safes table
        camId = 4 -- alerts the cops with the camera number to view
    }
}
```

### Safes

!!! info
    If safe type is keypad, then it will open the keypad UI to enter a password or if the type is padlock then it will start the UI for the safecracker mini game


```lua
Config.Safes = {
    [1] = {
        vector4(-43.43, -1748.3, 29.42, -- safe location
        type = "keypad", -- safe type keypad/padlock
        robbed = false, -- dynamically changed, don't edit
        camId = 4 -- alerts the cops with the camera number to view
    }
}
```
