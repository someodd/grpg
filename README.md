# grpg: MMORPG literally in gopherspace

Multiplayer RPG game where you wander around the Internet Gopher Protocol. When you find a place in gopherspace nobody has been to before you get loot.

A single Literate Haskell script you can add to your gopherhole.

Active on gopher://gopher.someodd.zip/

## Installing

You can probably just do something like `sudo apt get install ghc`.

Then you can wire it up to your Gopher daemon. In my [Venusia](https://github.com/someodd/venusia) I do this:

```
[[gateway]]
selector = "/gateway/games/grpg/proxy/*"
search = false
wildcard = true
menu = false
command = "/var/gopher/output/grpg"
arguments = ["$wildcard"]

[[gateway]]
selector = "/gateway/games/grpg/look/*"
search = false
wildcard = true
menu = false
command = "/var/gopher/output/grpg"
arguments = ["$wildcard:look"]

[[gateway]]
selector  = "/gateway/games/grpg/cmd/*"
wildcard  = true
menu      = false
search    = true
command   = "/var/gopher/output/grpg"
arguments = ["$wildcard", "$search"]
```
