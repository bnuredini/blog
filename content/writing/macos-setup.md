+++
title = 'How I set up macOS for Programming'
date = 2026-08-29
+++

# How I set up macOS for Programming
 
Change the keyboard input source to U.S.: System Settings -> Keyboard -> Input Sources -> Edit... ->
Click on the "+" button -> Select English -> Select U.S. -> Add.

Change the keyboard settings to use F1, F2, etc. as the standard function keys: System Settings ->
Keyboard -> Turn on Use F1, F2, etc. keys as standard function keys.

Install Homebrew:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Install a couple of useful programs:

```
brew install neovim fish fnm fzf fd bat tokei zoxide rg yazi stow exiftool jq fx gh git-lfs btop ffmpeg-full imagemagick font-symbols-only-nerd-font poppler yt-dlp syncthing postgresql@16
brew install --cask ghostty iterm2 rectangle hammerspoon pika shottr zed dbeaver-community syncthing-app hammerspoon zen helium-browser ungoogled-chromium steipete/tap/codexbar iina stats brave-browser 
```

Set fish as the default shell:

```
echo /opt/homebrew/bin/fish | sudo tee -a /etc/shells
chsh -s /opt/homebrew/bin/fish
```

Install fisher & nvm:

<!-- TODO: Do we need nvm considering we've installed fnm? -->

```
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher
fisher install jorgebucaran/nvm.fish
```

Install Codex:

```
npm i -g @openai/codex
```

Install Docker Desktop.

<!-- TODO: This won't start syncthing at boot -->
Configure `syncthing` to launch at system startup:

```
brew services start syncthing
```

Turn off the automatic brightness adjustments: System Settings -> Display -> Turn off Automatically
adjust brightness.

Update the screen locking settings:

1. Open System Settings.
2. Go to Lock Screen.
3. Set **Start Screen Saver when inactive** to **For 1 hour**.
4. Set **Turn display off on battery when inactive** to **For 1 hour**.
5. Set **Turn dispaly off on power adapter when inactive** to **For 1 hour**.

Prevent automatic sleeping: System Settings -> Battery -> Options... -> Turn off 'Prevent automatic
sleeping on power adapter when the display is off'.

Configure Control Center to show Keyboard Brightness: System Settings -> Control Center ->
Keyboard Brightness -> Turn on Show in Control Center.

Configure Control Center to display seconds: System Settings -> Control Center -> Clock Options ->
Turn on Display the time with seconds.

Don't show the wallpaper on the menu bar: System Settings -> Menu Bar -> Turn on 'Show menu bar
background'.

Update Dock settings by going to System Settings -> Desktop & Dock, and doing the following:

* Turn on Automatically hide and show the Dock
* Turn off Animate opening applications
* Turn off Show suggested and recent apps in Dock

Remove the default delay when trying to show the Dock:

```
defaults write com.apple.dock autohide-delay -float 0; killall Dock
defaults write com.apple.dock autohide-time-modifier -float 0; killall Dock
```

Update mouse settings: System Settings -> Mouse -> Turn off Natural scrolling.

Remove the Keyboard Viewer menu icon: Hover over the Keyboard Viewer icon on the menu bar -> Press
Command -> Drag the icon over to the desktop -> Let go of the mouse.

Disable Hot Corners: Open System Settings -> Desktop & Dock -> Hot Corners... -> Find the bottom-right
corner Change it from 'Quick Note' to '–' -> Done.

Update the Display settings to have more real estate: System Settings -> Displays -> Select the 'More
Space' option.

Configure iTerm2 to open with a shortcut to emulate Yakuake's behavior:

1. Open System Settings -> General -> Login Items -> Click + to add iTerm.
2. Open iTerm2 -> Settings -> Profiles -> Keys -> Check 'A hotkey opens a dedicated window...' ->
   Configure Hotkey Window -> Use F1.
3. In iTerm2's Settings -> Appearance -> Exclude from Dock and Command-Tab Application Switcher.
4. In iTerm2's Settings -> Profiles -> Windows -> Style -> Select Maximized.
5. In iTerm2's Settings -> Advanced -> Set 'Add status bar icon when excluded from dock?' to 'No'.

Configure [Hammerspoon](https://hammerspoon.org):

* Create `~/.hammerspoon/init.lua`
* Enable Accessibility: Open Hammerspoon -> Preferences -> Enabled Accessibility -> Turn on the
  toggle for Hammerspoon in System Settings -> Restart Hammerspoon.

Install Hyperkey from https://hyperkey.app.

Install MDV from https://www.mowglii.com/mdv.

Configured these apps to open at login by Open System Settings -> General → Login Items -> Click +
to add, and selecting:

* Stats
* Shottr
* Rectangle

Set MDV as the default app for openeing Markdown files in Finder: Open Finder -> Select a `.md` file
-> Get Info -> Open with -> Change All MDV.

Do the same thing for these file types as well:

* `.json` -> Zed
* `.mov` -> INNA

Update the default searching behavior in Finder: Open Finder -> Settings... (press Command-,) ->
Advanced -> Set 'When performing a search' to 'Search the Current Folder'.

Configure Shottr by going to Shottr -> Preferences and setting the following:

* Hotkeys -> Set 'Active window screenshot' to Control + Option + Commnad + S
* Hotkeys -> Set 'Instant Text/QR Recognition' to Control + Option + Commnad + S
