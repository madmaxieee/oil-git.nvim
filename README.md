# oil-git.nvim

Git status integration for [oil.nvim](https://github.com/stevearc/oil.nvim) that shows git status by coloring file names and adding status symbols.

## Features

- 🎨 **File name highlighting** - Colors files based on git status
- 📝 **Status symbols** - Shows git symbols at end of lines
- 🚀 **Real-time updates** - Automatically refreshes when git changes occur
- ⚡ **Performance optimized** - No caching, always fresh git status
- 🔄 **LazyGit integration** - Updates instantly when closing LazyGit or other git tools

## Installation

### With LazyVim

```lua
return {
  "benomahony/oil-git.nvim",
  dependencies = { "stevearc/oil.nvim" },
  opts = {}
}
```

### With other plugin managers

```lua
-- Packer
use {
  "benomahony/oil-git.nvim",
  requires = { "stevearc/oil.nvim" },
  config = function()
    require("oil-git").setup()
  end
}

-- Plug
Plug 'stevearc/oil.nvim'
Plug 'benomahony/oil-git.nvim'
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

## Git Status Display

| Status | Symbol | Color | Description |
|--------|---------|-------|-------------|
| **+** | Added | Green | Staged new file |
| **~** | Modified | Yellow | Modified file (staged or unstaged) |
| **-** | Deleted | Red | Deleted file |
| **→** | Renamed | Purple | Renamed file |
| **?** | Untracked | Blue | New untracked file |
| **!** | Ignored | Gray | Ignored file |

## Auto-refresh Triggers

The plugin automatically refreshes git status when:

- Entering an oil buffer
- Buffer content changes (file operations in oil)
- Focus returns to Neovim (after using external git tools)
- Window focus changes
- Terminal closes (LazyGit, fugitive, etc.)
- Git plugin events (GitSigns, Fugitive)

## Commands

- `:lua require("oil-git").refresh()` - Manually refresh git status

## Requirements

- Neovim >= 0.8
- [oil.nvim](https://github.com/stevearc/oil.nvim)
- Git

## License

MIT
