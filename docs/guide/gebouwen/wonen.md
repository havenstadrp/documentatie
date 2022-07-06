---
description: Welcome to your complimentary apartment
---

# 🏨 qb-apartments

## Introduction

* This resource manages the apartment system for players. It uses qb-interior to spawn shells at a specific set of coordinates and functions the same as housing except by default the apartments do not cost any money

## Preview

![](<../../assets/images/image (3).png>)

## Configuration

```lua
Apartments = {}
Apartments.Starting = true/false -- Enable or disable starting apartments
Apartments.SpawnOffset = 30 -- How far under the map the apartment shell will spawn
Apartments.Locations = { -- Create new apartment locations
    ["apartment1"] = {
        name = "apartment1", -- The apartment name that saves in the database
        label = "South Rockford Drive", -- The label of the apartment (shown in preview)
        coords = { -- The apartment entrance location
            enter = vector4(-667.02, -1105.24, 14.63, 242.32),
        },
        polyzoneBoxData = { -- The polyzone box information for the entrance
            heading = 245,
            minZ = 13.5,
            maxZ = 16.0,
            debug = false,
            length = 1,
            width = 3,
            distance = 2.0,
            created = false
        }
    },
}
```







---
description: Buy & customize your dream home!
---

# 🏡 qb-houses

## Introduction

* Allows players to purchase homes that are created by those with the real-estate job. They can decorate them, have a personal garage and share keys with their friends

!!! info
    By default, this resource uses the 16 free shells found in [qb-interior.md](qb-interior.md "mention")


## Preview

![Viewing a house will bring up this UI which shows the cost and buy/cancel buttons](https://camo.githubusercontent.com/c5c5874ac7afb5cadd01e0d0bc89ce1ec253603b2ccf357d4a757ced724f625e/68747470733a2f2f696d6775722e636f6d2f3465516e5271412e706e67)

![Use the radial menu to set locations in your house such as stash and outfit access](https://camo.githubusercontent.com/ac17292df498da4a01df3e5362d4d37c110c43a7896f5fa161d79aaba078738c/68747470733a2f2f696d6775722e636f6d2f475470616c59572e706e67)

![Personalize your house by using the in-game decorator](https://camo.githubusercontent.com/fc66647c3b51a173e277dfd20cf5265146a66ee7b470e37d1ea5713fa34008d4/68747470733a2f2f696d6775722e636f6d2f666d563067504d2e706e67)

## Configuration

### Generic

```lua
Config = {}
Config.MinZOffset = 30 -- how far under the ground shells will spawn
Config.RamsNeeded = 2 -- how many stormram items are needed to raid a house
Config.UnownedBlips = false -- enable/disable unowned house blips on the map
Config.Houses = {} -- populates automatically on server start
Config.Targets = {} -- populates automatically on server start
Config.Furniture = {} -- pre-filled with tons of options
```

### Shells

* Found in qb-houses/client/main.lua at line 697

```lua
local function getDataForHouseTier(house, coords)
```

## Commands

* /decorate - Allows the player decorate the house
* /createhouse \[price] \[tier] - Creates a house and saves it to database
* /addgarage - Adds a garage to nearby house
* /enter - Enters the nearby house
* /ring - Rings the bell of nearby house

## Items

* police\_stormram - Allows on-duty police to enter and search a player's home







---
description: Which shell will it be?
---

# 🏠 qb-interior

## Introduction

* Handles all the logic for spawning shell models by exporting functions that can be called in other client-side files

## Configuration

!!! info
    This resource requires no configuration unless you want to add more exports


## What's included?

!!! info
    The below pdf file shows which shell models come by default


{% file src="../../assets/images/k4mb1shellstarter.pdf" %}

!!! info
    Optionally, this resource comes pre-configured for all of [K4MB1](https://www.k4mb1maps.com/) shells!


## Usage example

```lua
RegisterCommand('spawnshell', function()
    local ped = PlayerPedId()
    local coords = GetEntityCoords(ped)
    local shell = exports['qb-interior']:CreateApartmentShell(coords)
end)
```
