# NumTabs

CSS-only tab numbering for Zen Browser. No JavaScript required!

## Features

- **Tab Numbers** - Each tab shows its position number (1, 2, 3...)
- **Theme Matching** - Automatically adapts to your Zen theme
- **Zero Config** - Works out of the box
- **Pure CSS** - No fx-autoconfig needed

## Installation

### Quick Install

1. Open Zen Browser
2. Go to `about:support` → **Open Profile Folder**
3. Create a `chrome` folder if it doesn't exist
4. Copy `numtabs.css` to the chrome folder
5. Create `userChrome.css` with:
   ```css
   @import "numtabs.css";
   ```
6. Restart Zen Browser

### Manual Install

```bash
# Find your profile
PROFILE=~/Library/Application\ Support/zen/Profiles/YOUR_PROFILE

# Create chrome folder
mkdir -p "$PROFILE/chrome"

# Copy CSS
cp numtabs.css "$PROFILE/chrome/"

# Create userChrome.css
echo '@import "numtabs.css";' > "$PROFILE/chrome/userChrome.css"

# Enable custom styles (if not already)
# Go to about:config → toolkit.legacyUserProfileCustomizations.stylesheets = true

# Restart Zen
```

## Themes

NumTabs automatically matches these Zen themes:

| Theme       | Badge Color | Active Color |
| ----------- | ----------- | ------------ |
| One Dark    | #3e4452     | #61afef      |
| Dracula     | #44475a     | #bd93f9      |
| Nord        | #4c566a     | #88c0d0      |
| Gruvbox     | #504945     | #fabd2f      |
| Catppuccin  | #45475a     | #cba6f7      |
| Tokyo Night | #3b4261     | #7aa2f7      |
| GitHub Dark | #484f58     | #58a6ff      |

## Customization

Edit the CSS variables at the top of `numtabs.css`:

```css
:root {
  --numtabs-num-color: #abb2bf; /* Number text */
  --numtabs-num-bg: #3e4452; /* Number background */
  --numtabs-active-bg: #61afef; /* Active tab */
  --numtabs-active-color: #282c34; /* Active text */
}
```

## How It Works

- Uses CSS counters to number tabs from left to right
- Pinned tabs are automatically excluded
- Works with compact mode and overflow

## Uninstall

Remove the `@import` line from your `userChrome.css` or delete the file.

## Requirements

- Zen Browser (any recent version)
- No dependencies!
