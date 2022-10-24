# cpp-javadoc

## Disclaimer
This is the creation of https://github.com/zhou-michael, I am fixing some
problems with installation

## Overview
Plugin that inserts Javadoc style comments for cpp files using Treesitter.

## Installation

using [Packer](https://github.com/wbthomason/packer.nvim)
```lua
use 'Incorrectish/cpp-javadoc'
```

using [vim-plug](https://github.com/junegunn/vim-plug)
```vim
Plug 'Incorrectish/cpp-javadoc'
```

## Usage

### The `:Javadoc` command
While hovering over a function in c++ (anywhere in the function), the `:Javadoc` command will create a Javadoc above the function. Uses treesitter to find the parameter names.

Using `<C-j>` (or a custom keybinding) will achieve the same effect.

### Alignment
Parameter descriptions can be optionally aligned:
```cpp
/** Description.

@param    var_a       | <- Description starts here
@param    var_aaa     | <- aligned on this column
@param    var_aaaa    | <- based on the longest variable name.
*/
```

## Configuration
```lua
require('cpp-javadoc').setup({
    -- your options here
})
```
Or pass in no arguments for default configuration.
```lua
require('cpp-javadoc').setup()
```

## Options
default configuration:
```lua
{
    add_javadoc = '<C-j>', -- keybinding to add javadoc
    silent = true, -- whether or not to print error messages
    align = true, -- whether or not to align parameter descriptions
    left_spaces = 4, -- number of spaces between @param tag and parameter name
    right_spaces = 4, -- number of spaces between parameter name and description
}
```
