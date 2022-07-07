---
description: Welcome to your complimentary apartment
---

# 🏨 qb-apartments

## Introduction

* This resource manages the apartment system for players. It uses qb-interior to spawn shells at a specific set of coordinates and functions the same as housing except by default the apartments do not cost any money

## Preview

![](<../../assets/images/appartement.png>)

## Configuration


# 🏡 qb-houses

## Introduction

* Allows players to purchase homes that are created by those with the real-estate job. They can decorate them, have a personal garage and share keys with their friends



## Preview

![Viewing a house will bring up this UI which shows the cost and buy/cancel buttons](https://camo.githubusercontent.com/c5c5874ac7afb5cadd01e0d0bc89ce1ec253603b2ccf357d4a757ced724f625e/68747470733a2f2f696d6775722e636f6d2f3465516e5271412e706e67)

![Use the radial menu to set locations in your house such as stash and outfit access](https://camo.githubusercontent.com/ac17292df498da4a01df3e5362d4d37c110c43a7896f5fa161d79aaba078738c/68747470733a2f2f696d6775722e636f6d2f475470616c59572e706e67)

![Personalize your house by using the in-game decorator](https://camo.githubusercontent.com/fc66647c3b51a173e277dfd20cf5265146a66ee7b470e37d1ea5713fa34008d4/68747470733a2f2f696d6775722e636f6d2f666d563067504d2e706e67)



## Commands

* /decorate - Allows the player decorate the house
* /createhouse \[price] \[tier] - Creates a house and saves it to database
* /addgarage - Adds a garage to nearby house
* /enter - Enters the nearby house
* /ring - Rings the bell of nearby house

## Items

* police\_stormram - Allows on-duty police to enter and search a player's home


# 🏠 qb-interior

## Introduction

* Handles all the logic for spawning shell models by exporting functions that can be called in other client-side files

