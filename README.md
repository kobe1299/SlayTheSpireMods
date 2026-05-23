Language files for these Slay the Spire mods:
  
- Red: https://steamcommunity.com/sharedfiles/filedetails/?id=3032112884
- Green: https://steamcommunity.com/sharedfiles/filedetails/?id=3219969350
- Blue: https://steamcommunity.com/sharedfiles/filedetails/?id=2970853759
- Purple: https://steamcommunity.com/sharedfiles/filedetails/?id=3342218134

# Translation Guide

## Card Strings

### General
Information about card titles and descriptions is stored in the card strings file. A typical card looks like this:

```
"kobePurple:Ward": {
  "NAME": "Ward",
  "DESCRIPTION": "Gain Block equal to twice the amount of [W] gained this turn.",
  "UPGRADE_DESCRIPTION": "Gain Block equal to twice the amount of [W] gained this turn +!M!.",
  "EXTENDED_DESCRIPTION": [" NL (!B! Block)"]
},
```

EXTENDED_DESCRIPTION contains any additional text used outside the card. Use cases include the hint message for Invisible Threads, the block amount preview for Cloaking Shadows, and the speech bubble lines for Decoy.

Leave the dictionary keys (the first line and all caps strings) untouched, and translate everything else.



### Symbols
  Below are the special symbols used in card descriptions. Do not alter them.

  ```
    [R] [G] [B] [W]: Single energy symbol. Red/Green/Blue/Purple respectively.
  
    !D!: Damage
    
    !B!: Block

    !M!: Other numerical values, such as debuff duration and draw count
    
    !kobeBlue:SecondMagic!: Same as above
    
    *: Manual word highlight. Keywords are highlighted automatically, so this is mainly for created cards like Shivs.

    NL: Manual line break. These are optional and you can add/remove/relocate them however you want. In practice though, you're only going to use them for visual separation between unrelated card effects as the game can handle long texts on its own.
```

### Base Game Keywords
Special words such as Evoke and Block are called keywords. You need to format them properly so the game can recognize them, otherwise there will be no highlights or tooltips. They must be capitalized, and must be separated from the rest of the text with spaces, even in languages that normally do not use spaces.

If a keyword consists of two words in your language, replace the space with \u00A0.
  
```Translated\u00A0Keyword```

## Keyword Strings

Modded keywords are defined in the keyword strings file. They work differently from base game keywords. The English version uses two of them because the text box was too small to explain everything in. If you can put all the information on the card description, do so. Just forget about keywords and leave the keyword file empty. On the other hand, you can create your own keywords if you need to.

You will need to translate PROPER_NAME, NAMES, and DESCRIPTION.

I actually know very little about how they work, so I'm just quoting the [template mod](https://github.com/Gremious/StS-DefaultModBase/blob/master/theDefault/src/main/java/theDefault/DefaultMod.java) I used. You might also want to see [this page](https://github.com/Gremious/StS-DefaultModBase/blob/master/theDefault/src/main/resources/theDefaultResources/localization/eng/DefaultMod-Keyword-Strings.json).

> Keywords on cards are supposed to be Capitalized, while in Keyword-String.json they're lowercase
> 
> Multiword keywords on cards are done With_Underscores
> 
> If you're using multiword keywords, the first element in your NAMES array in your keywords-strings.json has to be the same as the PROPER_NAME.
> That is, in Card-Strings.json you would have #yA_Long_Keyword (#y highlights the keyword in yellow).
> In Keyword-Strings.json you would have PROPER_NAME as A Long Keyword and the first element in NAMES be a long keyword, and the second element be a_long_keyword


## Power Strings

### General
The power strings file describes what to show on the buff/debuff tooltips. Each power tooltip consists of multiple strings so that the game can insert varying numbers between them. Since the order of those numbers can not be changed, you will need to adapt your translation to fit the English format.

### Symbols
Power tooltips use different symbols from card descriptions:

```
#y: Colored word (yellow)

#b: Colored number (blue). You will often see this placed at the end of a string to color the following number.
```


# Applying Localization

Mods now support external language files and you can test and play without publishing your work. To use external files, locate the directory the mod is installed to, and place the three files in ```...\Steam\steamapps\workshop\content\[modID]\[language]``` ("kor" for Korean, "spa" for Spanish etc). Files must be UTF-8 encoded.

If you wish to share your work, publish your language files and notify me. I'll add them to the main mod.

If you need any further help, catch me on [Discord](https://discord.gg/GAnNc6d23Y).
