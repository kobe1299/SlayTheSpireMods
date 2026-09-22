Red: https://steamcommunity.com/sharedfiles/filedetails/?id=3032112884
Green: https://steamcommunity.com/sharedfiles/filedetails/?id=3219969350
Blue: https://steamcommunity.com/sharedfiles/filedetails/?id=2970853759
Purple: https://steamcommunity.com/sharedfiles/filedetails/?id=3342218134

You can localize any of these mods by translating Card-Strings.json, Keyword-Strings.json and Power-Strings.json.

Localization can be applied locally, or shared if you show it to me.

# Card-Strings.json

This file stores information about card titles and descriptions. A typical card looks like this:

```
"kobeBlue:Foo": {
  "NAME": "Foo",
  "DESCRIPTION": "Do something.",
  "UPGRADE_DESCRIPTION": "Do something twice.",
  "EXTENDED_DESCRIPTION": ["Additional text 1", "Additional text 2"]
},
```

To translate a card, translate every *** into your language.

```
"kobeBlue:Foo": {
  "NAME": "***",
  "DESCRIPTION": "***",
  "UPGRADE_DESCRIPTION": "***",
  "EXTENDED_DESCRIPTION": ["***", "***"]
},
```

EXTENDED_DESCRIPTION here contains any additional text for non-standard use. Use cases include the hint message for Fathom, the block amount preview for Ward, and the "I can't play this" speech bubble for Decoy.


## Symbols
  Below are the special symbols used in card descriptions. Most symbols require a space before and after it to work.

  ```
    [R] [G] [B] [W]: Red / Green / Blue / Purple Energy symbols. Each one of these is replaced with a single energy symbol.
  
    !D!: Damage value. The game calculate all damage modifiers and replace this with the correct value.
    
    !B!: Block value

    !M!: Miscellaneous numerical value, such as debuff duration and draw count
    
    !kobeBlue:SecondMagic!: Same as above. Used when a card requires two types of values.
    
    *: Manual word highlight. A word prefixed with an asterisk is colored yellow. Keywords are highlighted automatically, so this is mainly for created cards like Shivs.

    NL: Manual line break. These are optional and you can add/remove/relocate them however you want. Note that the game can handle long texts on its own.
```

## Base Game Keywords
A keyword is one of those special yellow words that brings up a popup when you hover over a card. In order for the game to recognize them, they must be formatted properly; each keyword must be capitalized, and must be separated from the rest of the text with spaces even in languages that normally do not use spaces.

If a keyword consists of two words in your language, replace the space with \u00A0.
Example: ```Translated\u00A0Keyword```

# Keyword-Strings.json

Modded keywords are defined in Keyword-String.json and work differently from base game ones. The English version of this mod series uses two modded keywords (Deck and Common) because the text box was too small. It's completely fine to leave this file empty if you can explain a card within its text box. On the other hand, you can create your own keywords if you need to.

I actually know very little about how this work, so I'm just quoting the [template mod](https://github.com/Gremious/StS-DefaultModBase/blob/master/theDefault/src/main/java/theDefault/DefaultMod.java) I used. [This page](https://github.com/Gremious/StS-DefaultModBase/blob/master/theDefault/src/main/resources/theDefaultResources/localization/eng/DefaultMod-Keyword-Strings.json) might be helpful as well.

> Keywords on cards are supposed to be Capitalized, while in Keyword-String.json they're lowercase
> Multiword keywords on cards are done With_Underscores
> If you're using multiword keywords, the first element in your NAMES array in your keywords-strings.json has to be the same as the PROPER_NAME.
> That is, in Card-Strings.json you would have #yA_Long_Keyword (#y highlights the keyword in yellow).
> In Keyword-Strings.json you would have PROPER_NAME as A Long Keyword and the first element in NAMES be a long keyword, and the second element be a_long_keyword


# Power-Strings.json

In the code, buffs and debuffs are called Powers (not to be confused with the card type). This file describes what to show on modded power tooltips. Each tooltip consists of multiple strings so the game can deal with plurals, and insert/update numbers when buffs/debuffs are applied/stacked. Since the order of those numbers is immutable, you will need to adapt your translation to fit the English format.

## Symbols
Power tooltips use different symbols from card descriptions:

```
#y: A word prefixed with this symbol is colored yellow. Mainly for keywords.

#b: Colors a word blue. Often placed at the end of a string so the number that follows becomes blue.
```


# Applying Localization

You can apply your localization without publishing it.

Locate the directory the mod is installed to, and place all three files in ```...\Steam\steamapps\workshop\content\[modID]\[language]``` folder. Files must be UTF-8 encoded.

Language code:
```
  German: deu
  Dutch: dut
  English: eng
  Esperanto: epo
  Finnish: fin
  French: fra
  Greek: gre
  Indonesian: ind
  Italian: ita
  Japanese: jpn (Try jpn2 if jpn doesn't work)
  Korean: kor
  Norwegian: nor
  Polish: pol
  Portuguese (Brazil): ptb
  Russian: rus
  Spanish: spa
  Croatian: srb
  Serbian: srp
  Thai: tha
  Turkish: tur
  Ukranian: ukr
  Vietnamese: vie
  Chinese (Simplified): zhs
  Chinese (Traditional): zht
```


# Sharing Localization

Publish your language files and notify me via the workshop page. I'll add your files to the main mod.

