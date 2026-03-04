# Bulgarian-Phonetic-Dvorak

After switching to Dvorak, one of the hardest and most inconvenient things to do
was to type using the ‘Bulgarian - Phonetic’ keyboard layout.
‘Bulgarian - Phonetic’ is tied to the QWERTY layout,
and is made so that each sound of the Latin alphabet would be matched
to the letter in the Cyrillic alphabet, which carries the same sound.
It is a very convenient layout for the QWERTY typists,
so I tried carrying over the concept and translating the Dvorak layout
into a ‘Bulgarian - Phonetic - Dvorak’ layout.

Here are all the new mappings: 

![Lowercase Layout](https://github.com/house-owl/Bulgarian-Phonetic-Dvorak/raw/master/layout_images/lowercase-layout.png)
![Uppercase Layout](https://github.com/house-owl/Bulgarian-Phonetic-Dvorak/raw/master/layout_images/uppercase-layout.png)
![Caplock Layout](https://github.com/house-owl/Bulgarian-Phonetic-Dvorak/raw/master/layout_images/caplock-layout.png)

## Installation

### macOS

    git clone https://github.com/house-owl/Bulgarian-Phonetic-Dvorak.git
    sudo cp Bulgarian-Phonetic-Dvorak/layout/* /Library/Keyboard\ Layouts/

The macOS layout was created using [Ukelele](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=ukelele).

### Linux

1. **Back up your current files:** (optional)

       cp /usr/share/X11/xkb/symbols/bg /usr/share/X11/xkb/symbols/bg.bak
       cp /usr/share/X11/xkb/rules/evdev.xml /usr/share/X11/xkb/rules/evdev.xml.bak

2. **Append the layout variant to the Bulgarian symbols file:**

       cat linux/bg_phonetic_dvorak >> /usr/share/X11/xkb/symbols/bg

3. **Register the variant in evdev.xml.**

   Find the `<name>bg</name>` section and its `<variantList>`. Add the following entry inside `<variantList>`, next to the other Bulgarian variants:

   ```xml
   <variant>
     <configItem>
       <name>phonetic_dvorak</name>
       <description>Bulgarian (phonetic Dvorak)</description>
     </configItem>
   </variant>
   ```

4. **Select the layout** in your desktop environment's keyboard settings - it will appear as **Bulgarian (phonetic Dvorak)**. Or test it from the terminal:

       setxkbmap -layout bg -variant phonetic_dvorak

> **Note:** These system files may be overwritten when the `xkeyboard-config` package is updated. Keep the backups so you can re-apply the changes if needed.

---

Feel free to improve it and submit your PRs.
