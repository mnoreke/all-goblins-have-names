# All Goblins Have Names Reborn
[![Version (latest)](https://img.shields.io/github/v/release/mnoreke/all-goblins-have-names)](https://github.com/mnoreke/all-goblins-have-names/releases/latest)
[![Forge Installs](https://img.shields.io/badge/dynamic/json?label=Forge%20Installs&query=package.installs&suffix=%25&url=https%3A%2F%2Fforge-vtt.com%2Fapi%2Fbazaar%2Fpackage%2Fall-goblins-have-names-reborn&colorB=4aa94a)](https://forge-vtt.com/bazaar#package=all-goblins-have-names-reborn)
[![GitHub downloads (latest)](https://img.shields.io/badge/dynamic/json?label=Downloads@latest&query=assets[?(@.name.includes('zip'))].download_count&url=https://api.github.com/repos/mnoreke/all-goblins-have-names/releases/latest&color=green)](https://github.com/mnoreke/all-goblins-have-names/releases/latest)

A module for Foundry VTT. Allows you to use a rolltable as the Display Name for a token so each new
token will get a random name. It can also roll random biographies for tokens when used with [Better Rolltables](https://foundryvtt.com/packages/better-rolltables/).

## Reborn Status

I picked this module up in December 2023 as it hadn't been updated in a while. I have it working for what I need for DnD5e. Anything else that doesn't work will be reviewd at as bug reports come in here on GitHub.

## How to use it

First, grab your random name table and drag it into a Journal entry. That will give you some
text that looks similar to `@UUID[RollTable.OfTzIzGy7fyCgGz7]{Elf First Name}`. Now, open the Actor
and click Prototype Token. Paste your `@UUID[RollTable...` text into the Token Name. When you drag your Actor
onto the map to create a new Token, its name will be randomized!

If you are working directly with a compendium, then the string will instead look like `@UUID[Compendium.monks-enhanced-journal.person-names.RollTable.AQBywLCajYDmBTay]{Dwarf Last Name}`.

### Return more than one result for firstname + lastname

When multiple lines are returned from a table, the lines will be joined together with a space. For example, you could have a roll table formula of 1d1, and have two results which are also tables for a firstname and a lastname, both with range 1-1.

![A RollTable that returns multiple lines on the same dice roll, for firstname and lastname](./example.png)

## Random biographies with Better Rolltables

Story tables are currently bugged in Better Rolltables. When this changes, we will update this README with instructions on how to randomize biographies.

## API

This module provides a few methods under the `game.allGoblinsHaveNames` namespace for use in macros or other modules.

- `game.allGoblinsHaveNames.rerollSelectedTokens()` - Re-rolls the names of all selected tokens.
- `game.allGoblinsHaveNames.rollFromTableString(tableStr)` - Takes a string like `@RollTable[...` or `@Compendium[...` and returns a random result from that table.

## Installation

You can install this module through the Foundry module UI.

## Get help

You can [file an issue](https://github.com/mnoreke/all-goblins-have-names/issues/new) on github if
you're running into a bug or reach me on the Foundry VTT discord as Gandamir.
