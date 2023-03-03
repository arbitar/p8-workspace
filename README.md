# Blank PICO-8 workspace

I just want VS Code to look and act like the PICO-8 code editor.

![preview after application](https://raw.githubusercontent.com/arbitar/p8-workspace/master/.vscode/preview.gif)

Nothing too fancy, I like the experience as it is... but just with more vertical space. And maybe the ability to split tabs. And maybe a better search/replace.

So, I started editing. Everything is in the .vscode/ directory. You can download a ZIP of this repository and extract it to where you'd like to work on PICO-8 carts. There is some manual setup, outlined below, but after you finish that, it will take effect automatically anytime you open the directory containing the .vscode folder.

This is largely just a collection of other people's utilities, tied together with an ugly settings.json file. I hope it's helpful.

# Quick Install
1. Download ZIP of this repo. Unzip wherever you'd like to work on P8 carts.  
2. Install Pico-8 font by RhythmLynx: ./vscode/pico_8.ttf
3. Install 2 VS Code extensions:  
  \-> [pico8-vscode by John Barton](https://marketplace.visualstudio.com/items?itemName=johob.pico8-vscode)  
  \-> [Insert Unicode by brunnerh](https://marketplace.visualstudio.com/items?itemName=brunnerh.insert-unicode)
4. Copy contents of .vscode/keybindings.json into your global keybindings -- **right before the final `]`**!
	- Access via Ctrl+Shift+P > "Preferences: Open Keyboard Shortcuts (JSON)"
5. Open directory (with this README.md) in vs code
6. Enjoy!

# Details

## Font: .vscode/pico_8.ttf

A user by the name of RhythmLynx had uploaded a great set of PICO-8 fonts on the BBS [here](https://www.lexaloffle.com/bbs/?tid=3760). I used one of these and installed it on my system to give VS Code access to it. I modified the TTF to rename the font from "MyFont" to "P8".

Sadly, since downloading it for my own use, it seems the Google Drive links have 404'd. I am thus including the font file here. Install the font, then you can use it in VS Code (or any other program) by selecting "P8" as your font.

## Syntax highlighting

VS Code does not know what to do with ".p8" files on its own ... so I install a VS Code extension: [pico8-vscode by John Barton](https://marketplace.visualstudio.com/items?itemName=johob.pico8-vscode). This informs VS Code, at least, of what language it is, and includes some of the non-LUA quirks like the single-line if statement. It's important for the keybinds later, too, since it identifies a p8 file as a "pico8" language.

## Keybinds

I really wanted to replicate the PICO-8's "shift key" insertions of Unicode characters in VS Code, I really like those. So, I found this extension, [Insert Unicode by brunnerh](https://marketplace.visualstudio.com/items?itemName=brunnerh.insert-unicode), which (among other things) allows one to bind hotkeys to insert Unicode symbols.

Sadly, VS Code does not allow defining workspace-specific hotkeys, so they need to go into your global keybindings.json file. They have 'when' blocks to limit their activation to only pico8 files. 

After installing the Insert Unicode extension above, Open the .vscode/keybindings.json file. Select all the lines between the first "[" and the last "]" - and copy them into your clipboard. Then, access your global keyboard shortcuts (Ctrl+Shift+P > "Preferences: Open Keyboard Shortcuts (JSON)"), and go all the way to the bottom of the file. Paste the keybinds you've copied before the final "]", and save. Done!


## Editor colors

PICO-8's garish color scheme simply must make an appearance in my editor. The .vscode/settings.json will take care of this for us. All the wonderful eye-searing colors have been pre-programmed into it. If you have the pico-8 syntax highlighting installed from above, it will just take care of it all for you.