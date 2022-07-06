---
description: Got any of that good stuff?
---

# 💊 qb-drugs

## Introduction

* Create dealers that players can interact with and purchase items or accept delivery jobs to earn rewards. Also included is "corner-selling" which allows players to sell drugs to NPC's for configured prices

## Configuration

### General

```lua
Config = {}
Config.Dealers = {} -- auto-populates on resource start
Config.MinimumDrugSalePolice = 2 -- minimum police allowed to corner sell
```

### Products

```lua
Config.Products = { -- products availabe to buy from a dealer
    [1] = {
        name = "weed_white-widow", -- item name
        price = 15, -- how much it costs
        amount = 150, -- amount available in stock
        info = {}, -- item info (none)
        type = "item", -- item type
        slot = 1, -- inventory slot item will show in
        minrep = 0, -- how much rep needed to buy this item
    },
}
```

### Corner selling item list

```lua
Config.CornerSellingDrugsList = { -- items available to be corner sold
    "weed_white-widow",
    "weed_skunk",
    "weed_purple-haze",
    "weed_og-kush",
    "weed_amnesia",
    "weed_ak47",
    "crack_baggy",
    "cokebaggy",
    "meth"
}
```

### Corner selling pricing

```lua
Config.DrugsPrice = {
    ["weed_white-widow"] = { -- item name (reference above)
        min = 15, -- minimum price could sell for
        max = 24, -- maximum price could sell for
    },
}
```

### Delivery locations

```lua
Config.DeliveryLocations = { -- List of deliveries players can get from dealers
    [1] = {
        ["label"] = "Stripclub", -- delivery location name
        ["coords"] = vector3(106.24, -1280.32, 29.24), -- delivery location coords
    },
}
```

### Delivery rewards

```lua
Config.DeliveryItems = { -- reward items for deliveries (reference above)
    [1] = {
        ["item"] = "weed_brick", -- item name
        ["minrep"] = 0, -- minimum rep needed to get this item
    },
}
```

## Commands

* /newdealer - Create a new dealer at your coordinates
* /deletedealer - Delete a dealer from the database
* /dealers - Get a list of current dealers
* /dealergoto - Teleport to a dealer






---
description: It's medicinal? Sure it is...
---

# 🌿 qb-weed

## Introduction

* Handles the logic for growing weed in a player-owned house
* Multi-stage growing (plant gets bigger overtime)
* Saves status in the SQL to be able to keep progress through restarts&#x20;

## Configuration

```lua
QBWeed.Plants = {
    ["og-kush"] = {
        ["label"] = "OGKush 2g", -- plant label shown in menu
        ["item"] = "weed_og-kush", -- item you get from the plant
        ["stages"] = {
            ["stage-a"] = "bkr_prop_weed_01_small_01c", -- prop for stage
            ["stage-b"] = "bkr_prop_weed_01_small_01b",
            ["stage-c"] = "bkr_prop_weed_01_small_01a",
            ["stage-d"] = "bkr_prop_weed_med_01b",
            ["stage-e"] = "bkr_prop_weed_lrg_01a",
            ["stage-f"] = "bkr_prop_weed_lrg_01b",
            ["stage-g"] = "bkr_prop_weed_lrg_01b",
        },
        ["highestStage"] = "stage-g" -- designate the highest stage for plant
    },
    ["amnesia"] = {
        ["label"] = "Amnesia 2g",
        ["item"] = "weed_amnesia",
        ["stages"] = {
            ["stage-a"] = "bkr_prop_weed_01_small_01c",
            ["stage-b"] = "bkr_prop_weed_01_small_01b",
            ["stage-c"] = "bkr_prop_weed_01_small_01a",
            ["stage-d"] = "bkr_prop_weed_med_01b",
            ["stage-e"] = "bkr_prop_weed_lrg_01a",
            ["stage-f"] = "bkr_prop_weed_lrg_01b",
            ["stage-g"] = "bkr_prop_weed_lrg_01b",
        },
        ["highestStage"] = "stage-g"
    },
    ["skunk"] = {
        ["label"] = "Skunk 2g",
        ["item"] = "weed_skunk",
        ["stages"] = {
            ["stage-a"] = "bkr_prop_weed_01_small_01c",
            ["stage-b"] = "bkr_prop_weed_01_small_01b",
            ["stage-c"] = "bkr_prop_weed_01_small_01a",
            ["stage-d"] = "bkr_prop_weed_med_01b",
            ["stage-e"] = "bkr_prop_weed_lrg_01a",
            ["stage-f"] = "bkr_prop_weed_lrg_01b",
            ["stage-g"] = "bkr_prop_weed_lrg_01b",
        },
        ["highestStage"] = "stage-g"
    },
    ["ak47"] = {
        ["label"] = "AK47 2g",
        ["item"] = "weed_ak47",
        ["stages"] = {
            ["stage-a"] = "bkr_prop_weed_01_small_01c",
            ["stage-b"] = "bkr_prop_weed_01_small_01b",
            ["stage-c"] = "bkr_prop_weed_01_small_01a",
            ["stage-d"] = "bkr_prop_weed_med_01b",
            ["stage-e"] = "bkr_prop_weed_lrg_01a",
            ["stage-f"] = "bkr_prop_weed_lrg_01b",
            ["stage-g"] = "bkr_prop_weed_lrg_01b",
        },
        ["highestStage"] = "stage-g"
    },
    ["purple-haze"] = {
        ["label"] = "Purple Haze 2g",
        ["item"] = "weed_purple-haze",
        ["stages"] = {
            ["stage-a"] = "bkr_prop_weed_01_small_01c",
            ["stage-b"] = "bkr_prop_weed_01_small_01b",
            ["stage-c"] = "bkr_prop_weed_01_small_01a",
            ["stage-d"] = "bkr_prop_weed_med_01b",
            ["stage-e"] = "bkr_prop_weed_lrg_01a",
            ["stage-f"] = "bkr_prop_weed_lrg_01b",
            ["stage-g"] = "bkr_prop_weed_lrg_01b",
        },
        ["highestStage"] = "stage-g"
    },
    ["white-widow"] = {
        ["label"] = "White Widow 2g",
        ["item"] = "weed_white-widow",
        ["stages"] = {
            ["stage-a"] = "bkr_prop_weed_01_small_01c",
            ["stage-b"] = "bkr_prop_weed_01_small_01b",
            ["stage-c"] = "bkr_prop_weed_01_small_01a",
            ["stage-d"] = "bkr_prop_weed_med_01b",
            ["stage-e"] = "bkr_prop_weed_lrg_01a",
            ["stage-f"] = "bkr_prop_weed_lrg_01b",
            ["stage-g"] = "bkr_prop_weed_lrg_01b",
        },
        ["highestStage"] = "stage-g"
    },
}

QBWeed.Props = { -- prop list to check if near to allow/deny planting
    ["stage-a"] = "bkr_prop_weed_01_small_01c",
    ["stage-b"] = "bkr_prop_weed_01_small_01b",
    ["stage-c"] = "bkr_prop_weed_01_small_01a",
    ["stage-d"] = "bkr_prop_weed_med_01b",
    ["stage-e"] = "bkr_prop_weed_lrg_01a",
    ["stage-f"] = "bkr_prop_weed_lrg_01b",
    ["stage-g"] = "bkr_prop_weed_lrg_01b",
}
```
