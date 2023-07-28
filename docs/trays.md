---
nav_order: 3
title: Trays and Tiles
layout: default
permalink: trays
---

# Trays and Tiles

Trays are ERC721 NFTs consisting of 7 tiles (characters) chosen deterministically during minting from a pool of 909 arbitrarily weighted unicode characters. They can be minted with the `buy` method on `Tray.sol` for a fixed fee or traded on the secondary market.

Tray NFTs have no supply cap. For a given tokenId, `tokenURI` view renders an SVG preview of the tray:

| **Example 1** | **Example 2** |
|-|-|
| ![Example Tray 1](../assets/sample_tray1.svg) | ![Example Tray 2](../assets/sample_tray2.svg) |

## Tiles

Tiles are unicode characters including stylized and unstylized Latin letters, numbers, and emojis. When a tray is minted, each tile is chosen deterministically from one of nine weighted categories. Within each category, characters have the same weight.

The categories are:


| **Index** | **Name**        | **Weight** | **Characters** |
|:--|:--|:--|:----------------|
| 0 | Emoji*           | 32 | ✨✅❗⚡☕⭐❌⚽❓⏰⭕⚫⚾☔⚪✋✊😂🤣😭😘🥰😍😊🎉😁💕🥺😅🔥🙄😆🤗😉🎂🤔🙂😳🥳😎💜😔💖👀😋😏😢💗😩💯🌹💞🎈💙😃😡💐😜🙈😄🤤🤪😀💋💀💔😌💓🤩🙃😬😱😴🤭😐🌞😒😇🌸😈🎶🎊🥵😞💚🖤💰😚👑🎁💥😑🥴💩🤮😤🤢🌟😥🌈💛😝😫😲🔴🌻🤯🤬😕🍀💦🦋🤨🌺😹🌷💝💤🐰😓💘🍻😟😣🧐😠🤠😻🌙😛🙊🧡🤡🤫🌼🥂😷🤓🥶😶😖🎵😙🍆🤑😗🐶🍓👅👄🌿🚨📣🍑🍃😮💎📢🌱🙁🍷😪🌚🏆🍒💉💢🛒😸🐾🚀🎯🍺📌📷💨🍕🏠📸🐇🚩😰🌊🐕💫😵🎤🏡🥀🤧🍾🍰🍁😯💌💸🧁😺💧💣🤐🍎🐷🐥📍🎀🥇🌝🔫🐱🐣🎧💟👹💍🍼💡😽🍊😨🍫🧢🤕🚫🎼🐻📲👻👿🌮🍭🐟🐸🐝🐈🔵🔪😧🌄😾📱🍇🌴🐢🌃👽🍌📺🔔🌅🦄🎥🍋🥚💲📚🐔🎸🥃😿🚗🌎🔊🦅🚿🦆🍉🍬🧸🍨📝📩💵💭🌍🍿🧿🏀🍏🌳🙉😦🍹🍦🛑🍔🍂🐒🍪🙀🍗🌠🎬🌵🍄🐐🍩🦁📞🍅🐍💬🥤😼🌾🧀🎮🧠🌏🔝🌉🤒👗🌲🍜🐦🍯🏅🐼💄👺🔞🎆🎨🍞🎇🦜🐑🐙🦍🔗📖🔹🥓🥒🍸👍🙏🤦🤷👏👌💪👉🤞🙌👇🙋👈👋🖕💃👊🏃🤘🤝🤙🚶💅🤟👎🙇👶🤲👆🕺💁🙅🧚🤸👐🤚👼👧🤜🤰🧘🙆👸👦🛌🤛👮❤️☺️♥️❣️✌️☀️☹️‼️☠️➡️⚠️✔️☝️⬇️❄️⁉️☎️✝️☘️✈️▶️✍️⬅️☁️☑️♻️👁️🖐️🗣️🌧️🕊️🏵️🏖️🇺🇸🇧🇷🇺🇲🏳️‍🌈 |
| 1 | Basic           | 32 | abcdefghijklmnopqrstuvwxyz0123456789 |
| 2 | Script          | 16 | 𝒶𝒷𝒸𝒹𝑒𝒻𝑔𝒽𝒾𝒿𝓀𝓁𝓂𝓃𝑜𝓅𝓆𝓇𝓈𝓉𝓊𝓋𝓌𝓍𝓎𝓏 |
| 3 | Script Bold     | 8 | 𝓪𝓫𝓬𝓭𝓮𝓯𝓰𝓱𝓲𝓳𝓴𝓵𝓶𝓷𝓸𝓹𝓺𝓻𝓼𝓽𝓾𝓿𝔀𝔁𝔂𝔃 |
| 4 | Olde            | 8 | 𝔞𝔟𝔠𝔡𝔢𝔣𝔤𝔥𝔦𝔧𝔨𝔩𝔪𝔫𝔬𝔭𝔮𝔯𝔰𝔱𝔲𝔳𝔴𝔵𝔶𝔷 |
| 5 | Olde Bold       | 4 | 𝖆𝖇𝖈𝖉𝖊𝖋𝖌𝖍𝖎𝖏𝖐𝖑𝖒𝖓𝖔𝖕𝖖𝖗𝖘𝖙𝖚𝖛𝖜𝖝𝖞𝖟 |
| 6 | Squiggle        | 4 | αႦƈԃҽϝɠԋιʝƙʅɱɳσρϙɾʂƚυʋɯxყȥ |
| 7 | <br>Zalgo**<br><br>           | 2          | a̷̢̝̫̭̐͒̇̅̉̌b̸̡̡̲̪̙͇̆͋̂̄̿̈́̄̈́̓c̶̫̱̐́̐̀͘d̷̳̟̮̼͙̫̬̫͎͎̎̾ẽ̸̋͜͝f̴̭͕̬̪͉̝̈́͘g̴̢͔̤͍̤̫̥̠̥̺̒ĥ̴̢̨̩͈͕̦̰͓̺͒͐͛į̴͖͙̳̻̓͊͊̚͠ͅj̶͙͖͉̪̍̿̈͝k̷̰͉͍͊̐͊͑̂̾̐͒̃͝ļ̸̥̬͉̳͖̋̾m̶̨̧̳͖̫̫̗͒̀̈́̿͝ͅǹ̸̛͙̲̺͒̏̑ȏ̵̺̘̬̭̘͑̌̏̄̑̂͐͠͝p̷̡̬͇̞̔͑̋̌̾̿q̶̡̼̙̲̳̰͈̊͗̂̈̄͊̒ͅř̷̛̰s̶̳̲̼͊̋̈́̑̌̒͌͝͝t̵̆̾̌͌͘ͅu̷̥̫̹̔͜v̶̻̤̥́̅́͠w̷̢͕̩̤̬̮̙̪͈̲̐͂͊͒͋̐̚͠͝x̶̝̠̺̻̱͋͒̊͝y̵̢̥̟̭̯̫̲͐̃̈́͘ͅz̴͙̖͌͋̋͒̿̾̇̎͘͝|
| 8 | Blocks          | 2 | 🄰🄱🄲🄳🄴🄵🄶🄷🄸🄹🄺🄻🄼🄽🄾🄿🅀🅁🅂🅃🅄🅅🅆🅇🅈🅉 |
| 9 | Blocks Inverted | 1 | 🅰🅱🅲🅳🅴🅵🅶🅷🅸🅹🅺🅻🅼🅽🅾🅿🆀🆁🆂🆃🆄🆅🆆🆇🆈🆉 |

* For emojis that support skin tone modifiers, the following values can be specified *when fusing*:

| **Value** | **Modifier**        |
|:-----------|:---------------------|
| 0         | 👍 |
| 1         | 👍🏻 |
| 2         | 👍🏼 |
| 3         | 👍🏽 |
| 4         | 👍🏾 |
| 5         | 👍🏿 |

** Zalgo distortions are individually generated for every tile. The number of characters is therefore much higher, as every character can appear with different distortions.

## Prelaunch

Canto Namespace Protocol has a prelaunch phase during which 1000 Tray NFTs can be preminted for arbitrary distribution. These trays can only be fused during the prelaunch period, after which they become invalid and revert on `tokenURI` calls.