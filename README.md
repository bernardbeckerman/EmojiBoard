# EmojiBoard for Mac
Turn your USELESS caps-lock key into an emoji keyboard modifier! And yes I typed `USELESS` by holding shift down with my pinky 😜

Note: this also has the desirable side-effect of making it harder to auto-caps-lock by accident

# Instructions
## Part one: get emoji keybindings
* Open Terminal.app
* Type `mkdir ~/Library/KeyBindings/` and hit enter
* Put the file `DefaultKeyBinding.dict` into `~/Library/KeyBindings/`
    * Note: `~` is shorthand for your home directory
    * Tip: `~/Library/` is a hidden folder, but you can make it visible by typing `command + shift + .` at the same time
* *IMPORTANT:* Reload any applications you want to use these keybindings in

And _voila_! You should now be able to type emojis by holding down `shift + option + control` and typing any key

The current keyboard–emoji mapping is "optimized" for my personal usage (read into that what you like) and what I can more-or-less easily remember, but you can edit the contents of `DefaultKeyBinding.dict` to be whatever you like! A few tips when doing this:
    * To insert different emojis into `DefaultKeyBinding.dict`, type `command + control + space_bar` to bring up the MacOS emoji picker
    * Remember to reload any applications that are open in order for changes to `DefaultKeyBinding.dict` to take effect

## Part two: map caps_lock to `shift + option + control`
* Follow [this post](https://www.howtogeek.com/409904/how-to-turn-your-mac%E2%80%99s-caps-lock-into-an-extra-modifier-key/), excluding the section titled `A True Hyper Key` (we'll map to emojis instead!). Like the author, I use the method where `shift + caps_lock` maps to `caps_lock`.
* In `~/.config/karabiner/karabiner.json` there should be a few lines resembling:
```
"to": [
    {
        "key_code": "left_shift",
        "modifiers": [
            "left_command",
            "left_control",
            "left_option"
        ]
    }
],
```
Delete the line containing `"left_command",` and you're done!

## FAQ
*Why is part two so janky?*
That's how I did it. I should probably figure out how to contribute to karabiner so that ppl don't have to edit `karabiner.json` by hand but for now that's the way to do it. Pls feel free to contribute that and let me know so I can get rid of this mea culpa!

*For someone with an emoji keyboard, you don't seem to use them much. Shouldn't you have more emojis throughout this README?*
Yes that's a good point 😬🤣 I'll have to add some 🙂

*Why do you have an FAQ instead of just putting these all in Issues*
Ok apparently I am better at MacOS keyboard hacks than at using github correctly 🙃

*Why use `shift + option + control` instead of `command + shift + option + control`?*
Weird things were happening with the latter, e.g., commands actually executing, so I decided to stick with the former that I found to be mapped to `nothing`.

# References
* I 100% stole the idea for this project from [@MattDzugan](https://github.com/mattdzugan/qmk_firmware/blob/master/keyboards/massdrop/alt/keymaps/mattdzugan/keymap.c#L153-L158)
* I learned to edit default key bindings using [this gist](https://gist.github.com/trusktr/1e5e516df4e8032cbc3d)
* I learned about how to correctly format DefaultKeyBinding.dict on [this page](https://web.archive.org/web/20161220060333/http://osxnotes.net/keybindings.html) (thank heavens for the [waybackmachine](http://web.archive.org/))
* I learned about [karabiner-elements](https://karabiner-elements.pqrs.org/) from [this post](https://www.howtogeek.com/409904/how-to-turn-your-mac%E2%80%99s-caps-lock-into-an-extra-modifier-key/)
