# oil-git.nvim

Git status integration for [oil.nvim](https://github.com/stevearc/oil.nvim) that shows git status by coloring file names.

## Features

- Shows git status by coloring file names in oil.nvim
- Cached git status calls for performance
- Automatic refresh on buffer changes
- Customizable colors

## Installation

### With LazyVim

```lua
return {
  "benomahony/oil-git.nvim",
  dependencies = { "stevearc/oil.nvim" },
  opts = {}
}
```

### With lazy.nvim

```lua
{
  "benomahony/oil-git.nvim",
  dependencies = { "stevearc/oil.nvim" },
  config = function()
    require("oil-git").setup()
  end
}
```

## Configuration

```lua
require("oil-git").setup({
  highlights = {
    OilGitAdded = { fg = "#a6e3a1" },     -- green
    OilGitModified = { fg = "#f9e2af" },  -- yellow  
    OilGitDeleted = { fg = "#f38ba8" },   -- red
    OilGitRenamed = { fg = "#cba6f7" },   -- purple
    OilGitUntracked = { fg = "#89b4fa" }, -- blue
    OilGitIgnored = { fg = "#6c7086" },   -- gray
  }
})
```

## Git Status Colors

- **Green**: Added files
- **Yellow**: Modified files
- **Red**: Deleted files
- **Purple**: Renamed files
- **Blue**: Untracked files
- **Gray**: Ignored files

## Commands

- `:lua require("oil-git").refresh()` - Manually refresh git status

## Requirements

- Neovim >= 0.8
- [oil.nvim](https://github.com/stevearc/oil.nvim)
- Git
