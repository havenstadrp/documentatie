---
description: Truckin' and dumpin'
---

# 🚛 qb-truckerjob

## Introduction



!!! info
    This job is setup to restock random stores around the map as players complete deliveries!


## Configuration

### General

```lua
Config.BailPrice = 250 -- vehicle rental price

Config.Vehicles = { --Vehicles the job can rent to start their route
    ["rumpo"] = "Dumbo Delivery",
}
```

### Delivery locations




```lua
Config.Locations = {
    ["main"] = {
        label = "Truck Shed", -- map blip name
        coords = vector4(153.68, -3211.88, 5.91, 274.5), -- map blip location
    },
    ["vehicle"] = {
        label = "Truck Storage", -- map blip name
        coords = vector4(141.12, -3204.31, 5.85, 267.5), -- map blip location
    },
    ["stores"] ={
        [1] = {
            name = "ltdgasoline", -- store name referenced to qb-shops
            coords = vector4(-41.07, -1747.91, 29.4, 137.5), -- interact location
        },
        [2] = {
            name = "247supermarket",
            coords = vector4(31.62, -1315.87, 29.52, 179.5),
        },
    },
}
```
