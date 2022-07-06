---
description: Please! No more left turns!
---

# 🏁 qb-lapraces

## Introduction



## Preview

## Configuration

### General

```lua
Config = {}
Config.RaceSetupAllowed = true -- changes dynamically, don't edit this
Config.WhitelistedCreators = {
    "CITIZENID", -- List the player citizenid's allowed to create races
}
```

## Commands

* /cancelrace - Cancel the currently active race
* /togglesetup - Toggle the race creator


---
description: If you're not first, you're last
---

# 🏎 qb-streetraces

## Introduction

* Allows players to start street races using chat commands

!!! info
    Once a player creates a race, there will be some text drawn on the screen which prompts others to join


## Configuration

!!! info
    This resource requires no configuration and has no dependencies


## Commands

/createrace \[price] - Start a street race, join cost is the \[price]

/stoprace - Stop the race you created

/quitrace - Get out of a race, players payment is forfeited

/startrace - Starts the race player has created
