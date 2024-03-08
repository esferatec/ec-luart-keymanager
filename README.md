# ec-luart-keymanager

The project is a key management module written in Lua. It defines a KeyManager object that handles key gestures in LuaRT desktop applications.

[![Lua 5.4.6](https://badgen.net/badge/Lua/5.4.6/yellow)](https://github.com/lua/lua)
[![LuaRT 1.7.0](https://badgen.net/badge/LuaRT/1.7.0/blue)](https://github.com/samyeyo/LuaRT)
[![LuaCheck 1.1.1](https://badgen.net/badge/LuaCheck/1.1.1/green)](https://github.com/lunarmodules/luacheck)

## Features

The project provides a modular and flexible way to manage key events in desktop applications. It allows easy addition of widgets and their corresponding key gesture. The widget's onClick event is triggered by pressing the assigned key. Several key managers can be used in one application.

## Installation

1. Create a folder called "ecluart" in your application.
2. Copy the "km.lua" file into this folder.

```text
[application]
|
|----ecluart
|   |
|   |----km.lua
|   |----...
|
|----app.wlua
```

## Usage

The key manager (km) can be loaded using the function *require()*:

```lua
local km = require("ecluart.km") 
```

## Constructor

```lua
KeyManager() -> object
```

The code above initializes a new instance of the key manager. It returns the newly created object.

## Method - add

```lua
KeyManager:add(widget, key) -> none
```

This function allows the addition of a widget with a specific key to the KeyManager. It takes two parameters: widget (object) and key (string). It first validates the widget and key to ensure they meet the required criteria. If both the widget and key are valid, the function adds the widget to the self.children table with the specified key.

## Method - apply

```lua
KeyManager:apply(key) -> none
```

This function, named apply, processes the key input and performs specific actions accordingly. The apply function in the KeyManager class takes a key parameter, validates it, processes modifier keys, constructs the gesture, and triggers the associated event if applicable.

## License

Copyright (c) 2023 by esferatec.
It is open source, released under the MIT License.
See full copyright notice in the LICENSE.md file.
