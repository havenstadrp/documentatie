---
description: Best hookers in town!
---

# 🛻 qb-towjob

## Introduction

* Allows the player to rent a tow truck and accept calls from NPCs and players


## Configuration

### General

```lua
Config.BailPrice = 250 -- price to rent the job vehicle

Config.Vehicles = {
    ["flatbed"] = "Flatbed", -- checks this table for authorized vehicles
}

Config.Locations = {
    ["main"] = {
        label = "Towing HQ", -- map blip label
        coords = vector4(471.39, -1311.03, 29.21, 114.5), -- map blip location
    },
    ["vehicle"] = {
        label = "Flatbed", -- polyzone box name
        coords = vector4(489.65, -1331.82, 29.33, 306.5), -- vehicle withdraw
    },
}
```

### Locations

```lua
["towspots"] = { -- The car and coords of the NPC mission chosen at random
        [1] = {
                model = "sultanrs", -- vehicle model
                coords = vector3(-2480.87, -211.96, 17.39) -- vehicle location
              },
        },
        [2] = {
              model = "zion",
              coords = vector3(-2723.39, 13.20, 15.12)
              }
        }
}
```
