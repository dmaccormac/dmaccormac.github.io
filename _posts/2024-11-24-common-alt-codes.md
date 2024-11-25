---
title: How to quickly input special characters in Windows using Alt codes
date: 2024-11-24
tags:
  - alt codes
  - character sets
  - ansi
  - unicode
excerpt: A brief look at the history of Alt codes and a reference list of codes and their descriptions.  
---

# Introduction
Alt codes have their history rooted in the original IBM PC, released in 1981, which used a character set called Code Page 437. This set included all printable ASCII characters (0-127) and extended characters and symbols (128-255) [1, 2].  

Alt codes were first introduced in Windows 3.1 (1992) as a way for users to input these extended characters by holding down the Alt key and entering a code on the numeric keypad. While Unicode has come to replace these older character sets, the use of Alt codes is still supported in Windows 11. 

# Common codes

| Code |  Character   | Description    |
|-|-|-|
| Alt + 1 | ☺   | Smiley Face |
| Alt + 2 | ☻   | Dark Smiley Face |
| Alt + 3 | ♥   | Heart |
| Alt + 4 | ♦   | Diamond |
| Alt + 5 | ♣   | Club |
| Alt + 6 | ♠   | Spade |
| Alt + 7 | •   | Small Bullet Point |
| Alt + 8 | ◘   | Inverted Small Bulletpoint |
| Alt + 9 | ○   | Large Bullet Point |
| Alt + 10 | ◙   | Inverted Large Bullet Point |
| Alt + 11 | ♂   | Male Gender Symbol |
| Alt + 12 | ♀   | Female Gender Symbol |
| Alt + 13 | ♪   | Eighth Note |
| Alt + 14 | ♫   | Two Eighth Notes |
| Alt + 15 | ☼   | Sun |
| Alt + 16 | ►   | Block Right Arrow |
| Alt + 17 | ◄   | Block Left Arrow |
| Alt + 18 | ↕   | Up and Down Arrow |
| Alt + 19 | ‼   | Double Exclamation Mark |
| Alt + 20 | ¶   | New Paragraph Sign |
| Alt + 21 | §   | Section Sign |
| Alt + 22 | ▬   | Black Rectangle |
| Alt + 23 | ↨   | Up and Down Arrow With Base |
| Alt + 24 | ↑   | Up Arrow |
| Alt + 25 | ↓   | Down Arrow |
| Alt + 26 | →   | Right Arrow |
| Alt + 27 | ←   | Left Arrow |
| Alt + 28 | ∟   | Right Angle Symbol |
| Alt + 29 | ↔   | Left and Right Arrow |
| Alt + 30 | ▲   | Block Up Arrow |
| Alt + 31 | ▼   | Block Down Arrow |

# Code Page 437
Code Page 437 is an 8-bit character encoding used in the original IBM PC. It includes all printable ASCII characters (0-127)  and extended characters (128-255) such as accented letters.

![IBM Code Page 437](/assets/images/2024-11-24-alt-codes-1.png)

From the above chart, we can get the hex digits for the character by combining the first and second row numbers. For example, the rightward arrow charcter hexcode is 1A. If we convert this to base 10 we get 26, which is the matching Alt key code for → character.

# History of Windows code pages
Windows 1.0 (1985) came with a single character set known as the Windows ANSI character set. Windows 2.0 (1987) added missing characters like × and ÷ and  Windows 3.1 (1992) added 22 new characters. The term "ANSI" is a misnomer — while Windows code pages were initially based on drafts submitted to ANSI, they were never officially standardized. 

Over time, Windows introduced additional code pages to support different languages and regions. With the advent of Unicode, Windows gradually moved away from these code pages, providing a universal character set that supports virtually all languages. 

# Conclusion
Alt codes are an interesting example of how early computing solutions have had a lasting impact on how we interact with technology. In the early days of computing, they were widely used as a way to input extended characters and symbols. Although they are no longer the primary method for entering special characters in Windows, they still remain a simple and efficient way to enter symbols quickly.

# Glossary

| **Term** |  **Description**   | 
|-|-|
| (ASCII) American Standard Code Information Interchange | Character encoding standard used in computers to represent text | 
| (ANSI) American National Standards Institute | Non-profit organization that oversees the development of standards for systems |
| Unicode | Universal character encoding standard for handling text in most of the world's writing systems |

# References
[[1] CCSID information document](https://web.archive.org/web/20160327040039/http://www-01.ibm.com/software/globalization/ccsid/ccsid437.html)

[[2] Code Page CPGID 00437](https://web.archive.org/web/20211102114251/ftp://ftp.software.ibm.com/software/globalization/gcoc/attachments/CP00437.pdf)

[[3] Alt Code Unicode](https://altcodeunicode.com/)

[[4] Windows code page](https://en.wikipedia.org/wiki/Windows_code_page)


# Appendix
### Alt codes reference chart
[Windows-Alt-Codes-Reference-Chart.pdf](/assets/docs/Windows-Alt-Codes-Reference-Chart.pdf)

### List of Alt Codes

| **Alt Code** | **Character** | **Description** |
| --- | --- | --- |
| **Emoticons, Bullets, and Symbols** |     |     |
| Alt + 1 | ☺   | Smiley Face |
| Alt + 2 | ☻   | Dark Smiley Face |
| Alt + 3 | ♥   | Heart |
| Alt + 4 | ♦   | Diamond |
| Alt + 5 | ♣   | Club |
|     |     |     |
| Alt + 6 | ♠   | Spade |
| Alt + 7 / Alt + 0149 | •   | Small Bullet Point |
| Alt + 8 | ◘   | Inverted Small Bulletpoint |
| Alt + 9 | ○   | Large Bullet Point |
| Alt + 10 | ◙   | Inverted Large Bullet Point |
| Alt + 11 | ♂   | Male Gender Symbol |
| Alt + 12 | ♀   | Female Gender Symbol |
|     |     |     |
| Alt + 13 | ♪   | Eighth Note |
| Alt + 14 | ♫   | Two Eighth Notes |
| Alt + 15 | ☼   | Sun |
| Alt + 0153 | ™   | Trademark Symbol |
| Alt + 0169 | ©   | Copyright Symbol |
| Alt + 0174 | ®   | Registered Symbol |
| **Arrows and Angles** |     |     |
|     |     |     |
| Alt + 16 | ►   | Block Right Arrow |
| Alt + 17 | ◄   | Block Left Arrow |
| Alt + 18 | ↕   | Up and Down Arrow |
| Alt + 23 | ↨   | Up and Down Arrow With Base |
| Alt + 24 | ↑   | Up Arrow |
| Alt + 25 | ↓   | Down Arrow |
| Alt + 26 | →   | Right Arrow |
|     |     |     |
| Alt + 27 | ←   | Left Arrow |
| Alt + 28 | ∟   | Right Angle Symbol |
| Alt + 29 | ↔   | Left and Right Arrow |
| Alt + 30 | ▲   | Block Up Arrow |
| Alt + 31 | ▼   | Block Down Arrow |
| **Punctuation and Markup** |     |     |
| Alt + 19 | ‼   | Double Exclamation Mark |
|     |     |     |
| Alt + 20 / Alt + 0182 | ¶   | New Paragraph Sign |
| Alt + 21 / Alt + 0167 | §   | Section Sign |
| Alt + 33 | !   | Exclamation Mark |
| Alt + 34 | “   | Quotation Mark |
| Alt + 35 | #   | Number Sign |
| Alt + 38 | &   | Ampersand |
| Alt + 39 | ‘   | Apostrophe |
|     |     |     |
| Alt + 40 | (   | Open Parenthesis |
| Alt + 41 | )   | Close Parenthesis |
| Alt + 42 | \*  | Asterisk |
| Alt + 44 | ,   | Comma |
| Alt + 45 | \-  | Hyphen |
| Alt + 46 | .   | Period |
| Alt + 47 | /   | Slash |
|     |     |     |
| Alt + 58 | :   | Colon |
| Alt + 59 | ;   | Semi-Colon |
| Alt + 63 | ?   | Question Mark |
| Alt + 64 | @   | At Sign |
| Alt + 91 | \[  | Open Bracket |
| Alt + 92 | \\  | Backslash |
| Alt + 93 | \]  | Close Bracket |
|     |     |     |
| Alt + 94 | ^   | Caret |
| Alt + 95 | \_  | Underscore |
| Alt + 96 | \`  | Backtick |
| Alt + 123 | {   | Open Brace |
| Alt + 124 | \|  | Vertical Bar |
| Alt + 125 | }   | Close Brace |
| Alt + 166 / Alt + 0170 | ª   | Feminine Ordinal Indicator |
|     |     |     |
| Alt + 167 / Alt + 0186 | º   | Masculine Ordinal Indicator |
| Alt + 168 / Alt + 0191 | ¿   | Inverted Question Mark |
| Alt + 173 / Alt + 0161 | ¡   | Inverted Exclamation Mark |
| Alt + 174 / Alt + 0171 | «   | Open Double Angle Quotation Mark |
| Alt + 175 / Alt + 0187 | »   | Close Double Angle Quotation Mark |
| Alt + 250 / Alt + 0183 | ·   | Interpunct |
| Alt + 255 / Alt + 0160 |     | Space |
|     |     |     |
| Alt + 0130 | ‚   | Single Low Quotation Mark |
| Alt + 0132 | „   | Double Low Quotation Mark |
| Alt + 0133 | …   | Ellipsis |
| Alt + 0134 | †   | Dagger Mark |
| Alt + 0135 | ‡   | Double Dagger Mark |
| Alt + 0136 | ˆ   | Circumflex Mark |
| Alt + 0139 | ‹   | Open Single Angle Quotation Mark |
|     |     |     |
| Alt + 0145 | ‘   | Open Single Quotation Mark |
| Alt + 0146 | ’   | Close Single Quotation Mark |
| Alt + 0147 | “   | Open Double Quotation Mark |
| Alt + 0148 | ”   | Close Double Quotation Mark |
| Alt + 0150 | –   | En Dash |
| Alt + 0151 | —   | Em Dash |
| Alt + 0155 | ›   | Close Single Angle Quotation Mark |
|     |     |     |
| Alt + 0166 | ¦   | Vertical Bar |
| Alt + 0168 | ¨   | Diaeresis Sign |
| Alt + 0175 | ¯   | Macron Sign |
| Alt + 0180 | ´   | Accent Sign |
| Alt + 0184 | ¸   | Cedilla Sign |
| **Lines, Shapes, and Shades** |     |     |
| Alt + 22 | ▬   | Black Rectangle |
|     |     |     |
| Alt + 127 | ⌂   | House |
| Alt + 176 | ░   | Light Shade |
| Alt + 177 | ▒   | Medium Shade |
| Alt + 178 | ▓   | Dark Shade |
| Alt + 179 | │   | Vertical Box Drawing |
| Alt + 180 | ┤   | Vertical and Left Box Drawing |
| Alt + 181 | ╡   | Vertical Single and Left Double Box Drawing |
|     |     |     |
| Alt + 182 | ╢   | Vertical Double and Left Single Box Drawing |
| Alt + 183 | ╖   | Down Double and Left Single Box Drawing |
| Alt + 184 | ╕   | Down Single And Left Double Box Drawing |
| Alt + 185 | ╣   | Double Vertical and Left Box Drawing |
| Alt + 186 | ║   | Double Vertical Box Drawing |
| Alt + 187 | ╗   | Down Double and Left Single Box Drawing |
| Alt + 188 | ╝   | Double Up and Left Box Drawing |
|     |     |     |
| Alt + 189 | ╜   | Up Double and Left Single Box Drawing |
| Alt + 190 | ╛   | Up Single and Left Double Box Drawing |
| Alt + 191 | ┐   | Down and Left Box Drawing |
| Alt + 192 | └   | Up and Right Box Drawing |
| Alt + 193 | ┴   | Up and Horizontal Box Drawing |
| Alt + 194 | ┬   | Down and Horizontal Box Drawing |
| Alt + 195 | ├   | Vertical and Right Box Drawing |
|     |     |     |
| Alt + 196 | ─   | Horizontal Box Drawing |
| Alt + 197 | ┼   | Vertical and Horizontal Box Drawing |
| Alt + 198 | ╞   | Vertical Single and Right Double Box Drawing |
| Alt + 199 | ╟   | Vertical Double and Right Single Box Drawing |
| Alt + 200 | ╚   | Double Up and Right Box Drawing |
| Alt + 201 | ╔   | Double Down and Right Box Drawing |
| Alt + 202 | ╩   | Double Up and Horizontal Box Drawing |
|     |     |     |
| Alt + 203 | ╦   | Double Down and Horizontal Box Drawing |
| Alt + 204 | ╠   | Double Right and Vertical Box Drawing |
| Alt + 205 | ═   | Double Horizontal Box Drawing |
| Alt + 206 | ╬   | Double Vertical and Horizontal Box Drawing |
| Alt + 207 | ╧   | Up Single and Horizontal Double Box Drawing |
| Alt + 208 | ╨   | Up Double and Horizontal Single Box Drawing |
| Alt + 209 | ╤   | Down Single and Horizontal Double Box Drawing |
|     |     |     |
| Alt + 210 | ╥   | Down Double and Horizontal Single Box Drawing |
| Alt + 211 | ╙   | Up Double and Right Single Box Drawing |
| Alt + 212 | ╘   | Up Single and Right Double Box Drawing |
| Alt + 213 | ╒   | Down Single and Right Double Box Drawing |
| Alt + 214 | ╓   | Down Double and Right Single Box Drawing |
| Alt + 215 | ╫   | Vertical Double and Horizontal Single Box Drawing |
| Alt + 216 | ╪   | Vertical Single and Horizontal Double Box Drawing |
|     |     |     |
| Alt + 217 | ┘   | Up and Left Box Drawing |
| Alt + 218 | ┌   | Down and Right Box Drawing |
| Alt + 219 | █   | Full Block |
| Alt + 220 | ▄   | Lower Half Block |
| Alt + 221 | ▌   | Left Half Block |
| Alt + 222 | ▐   | Right Half Block |
| Alt + 223 | ▀   | Upper Half Block |
|     |     |     |
| Alt + 254 | ■   | Black Square |
| **Currency** |     |     |
| Alt + 36 | $   | Dollar Sign |
| Alt + 155 / Alt + 0162 | ¢   | Cent Sign |
| Alt + 156 / Alt + 0163 | £   | Pound Sterling Sign |
| Alt + 157 / Alt + 0165 | ¥   | Yen and Yuan Sign |
| Alt + 158 | ₧   | Peseta Sign |
|     |     |     |
| Alt + 0128 | €   | Euro Sign |
| Alt + 0164 | ¤   | Currency Sign |
| **Math** |     |     |
| Alt + 37 | %   | Percent Sign |
| Alt + 43 | +   | Plus Sign |
| Alt + 60 | <   | Less Than Sign |
| Alt + 61 | \=  | Equal Sign |
|     |     |     |
| Alt + 62 | \>  | Greater Than Sign |
| Alt + 126 | ~   | Tilde |
| Alt + 171 / Alt + 0189 | ½   | Vulgar Fraction One Half |
| Alt + 172 / Alt + 0188 | ¼   | Vulgar Fraction One Quarter |
| Alt + 236 | ∞   | Infinity Symbol |
| Alt + 239 | ∩   | Intersection |
| Alt + 240 | ≡   | Equivalent To Sign |
|     |     |     |
| Alt + 241 / Alt + 0177 | ±   | Plus-Minus Sign |
| Alt + 242 | ≥   | Greater Than or Equal To Sign |
| Alt + 243 | ≤   | Less Than or Equal To Sign |
| Alt + 244 | ⌠   | Top-Half Intergral Symbol |
| Alt + 245 | ⌡   | Bottom-Half Integral Symbol |
| Alt + 246 / Alt + 0247 | ÷   | Division Sign |
| Alt + 247 | ≈   | Almost Equal To Sign |
|     |     |     |
| Alt + 248 / Alt + 0176 | °   | Degree Sign |
| Alt + 249 | ∙   | Bullet Operator |
| Alt + 251 | √   | Square Root Sign |
| Alt + 252 | ⁿ   | Superscript Latin Small Letter N |
| Alt + 253 / Alt + 0178 | ²   | Squared Sign |
| Alt + 0137 | ‰   | Per Mille Sign |
| Alt + 0179 | ³   | Cubed Sign |
|     |     |     |
| Alt + 0185 | ¹   | Superscript Number One |
| Alt + 0190 | ¾   | Vulgar Fraction Three Quarters |
| Alt + 0215 | ×   | Multiplication Sign |
| **Alphanumeric Characters** |     |     |
| Alt + 48 | 0   | Digit Zero |
| Alt + 49 | 1   | Digit One |
| Alt + 50 | 2   | Digit Two |
|     |     |     |
| Alt + 51 | 3   | Digit Three |
| Alt + 52 | 4   | Digit Four |
| Alt + 53 | 5   | Digit Five |
| Alt + 54 | 6   | Digit Six |
| Alt + 55 | 7   | Digit Seven |
| Alt + 56 | 8   | Digit Eight |
| Alt + 57 | 9   | Digit Nine |
|     |     |     |
| Alt + 65 | A   | Latin Capital Letter A |
| Alt + 66 | B   | Latin Capital Letter B |
| Alt + 67 | C   | Latin Capital Letter C |
| Alt + 68 | D   | Latin Capital Letter D |
| Alt + 69 | E   | Latin Capital Letter E |
| Alt + 70 | F   | Latin Capital Letter F |
| Alt + 71 | G   | Latin Capital Letter G |
|     |     |     |
| Alt + 72 | H   | Latin Capital Letter H |
| Alt + 73 | I   | Latin Capital Letter I |
| Alt + 74 | J   | Latin Capital Letter J |
| Alt + 75 | K   | Latin Capital Letter K |
| Alt + 76 | L   | Latin Capital Letter L |
| Alt + 77 | M   | Latin Capital Letter M |
| Alt + 78 | N   | Latin Capital Letter N |
|     |     |     |
| Alt + 79 | O   | Latin Capital Letter O |
| Alt + 80 | P   | Latin Capital Letter P |
| Alt + 81 | Q   | Latin Capital Letter Q |
| Alt + 82 | R   | Latin Capital Letter R |
| Alt + 83 | S   | Latin Capital Letter S |
| Alt + 84 | T   | Latin Capital Letter T |
| Alt + 85 | U   | Latin Capital Letter U |
|     |     |     |
| Alt + 86 | V   | Latin Capital Letter V |
| Alt + 87 | W   | Latin Capital Letter W |
| Alt + 88 | X   | Latin Capital Letter X |
| Alt + 89 | Y   | Latin Capital Letter Y |
| Alt + 90 | Z   | Latin Capital Letter Z |
| Alt + 97 | a   | Latin Small Letter A |
| Alt + 98 | b   | Latin Small Letter B |
|     |     |     |
| Alt + 99 | c   | Latin Small Letter C |
| Alt + 100 | d   | Latin Small Letter D |
| Alt + 101 | e   | Latin Small Letter E |
| Alt + 102 | f   | Latin Small Letter F |
| Alt + 103 | g   | Latin Small Letter G |
| Alt + 104 | h   | Latin Small Letter H |
| Alt + 105 | i   | Latin Small Letter I |
|     |     |     |
| Alt + 106 | j   | Latin Small Letter J |
| Alt + 107 | k   | Latin Small Letter K |
| Alt + 108 | l   | Latin Small Letter L |
| Alt + 109 | m   | Latin Small Letter M |
| Alt + 110 | n   | Latin Small Letter N |
| Alt + 111 | o   | Latin Small Letter O |
| Alt + 112 | p   | Latin Small Letter P |
|     |     |     |
| Alt + 113 | q   | Latin Small Letter Q |
| Alt + 114 | r   | Latin Small Letter R |
| Alt + 115 | s   | Latin Small Letter S |
| Alt + 116 | t   | Latin Small Letter T |
| Alt + 117 | u   | Latin Small Letter U |
| Alt + 118 | v   | Latin Small Letter V |
| Alt + 119 | w   | Latin Small Letter W |
|     |     |     |
| Alt + 120 | x   | Latin Small Letter X |
| Alt + 121 | y   | Latin Small Letter Y |
| Alt + 122 | z   | Latin Small Letter Z |
| **Special Letters** |     |     |
| Alt + 128 / Alt + 0199 | Ç   | Latin Capital Letter C With Cedilla |
| Alt + 129 / Alt + 0252 | ü   | Latin Small Letter U With Diaeresis |
| Alt + 130 / Alt + 0233 | é   | Latin Small Letter E With Acute |
|     |     |     |
| Alt + 131 / Alt + 0226 | â   | Latin Small Letter A With Circumflex |
| Alt + 132 / Alt + 0228 | ä   | Latin Small Letter A With Diaeresis |
| Alt + 133 / Alt + 0224 | à   | Latin Small Letter A With Grave |
| Alt + 134 / Alt + 0229 | å   | Latin Small Letter A With Ring Above |
| Alt + 135 / Alt + 0231 | ç   | Latin Small Letter C With Cedilla |
| Alt + 136 / Alt + 0234 | ê   | Latin Small Letter E With Circumflex |
| Alt + 137 / Alt + 0235 | ë   | Latin Small Letter E With Diaeresis |
|     |     |     |
| Alt + 138 / Alt + 0232 | è   | Latin Small Letter E With Grave |
| Alt + 139 / Alt + 0239 | ï   | Latin Small Letter I With Diaeresis |
| Alt + 140 / Alt + 0238 | î   | Latin Small Letter I With Circumflex |
| Alt + 141 / Alt + 0236 | ì   | Latin Small Letter I With Grave |
| Alt + 142 / Alt + 0196 | Ä   | Latin Capital Letter A With Diaeresis |
| Alt + 143 / Alt + 0197 | Å   | Latin Capital Letter A With Ring Above |
| Alt + 144 / Alt + 0201 | É   | Latin Capital Letter E With Acute |
|     |     |     |
| Alt + 145 / Alt + 0230 | æ   | Latin Small Letter AE |
| Alt + 146 / Alt + 0198 | Æ   | Latin Capital Letter AE |
| Alt + 147 / Alt + 0244 | ô   | Latin Small Letter O With Circumflex |
| Alt + 148 / Alt + 0246 | ö   | Latin Small Letter O With Diaeresis |
| Alt + 149 / Alt + 0242 | ò   | Latin Small Letter O With Grave |
| Alt + 150 / Alt + 0251 | û   | Latin Small Letter U With Circumflex |
| Alt + 151 / Alt + 0249 | ù   | Latin Small Letter U Grave |
|     |     |     |
| Alt + 152 / Alt + 0255 | ÿ   | Latin Small Letter Y With Diaeresis |
| Alt + 153 / Alt + 0214 | Ö   | Latin Capital Letter O With Diaeresis |
| Alt + 154 / Alt + 0220 | Ü   | Latin Capital Letter U With Diaeresis |
| Alt + 159 / Alt + 0131 | ƒ   | Latin Small Letter F With Hook |
| Alt + 160 / Alt + 0225 | á   | Latin Small Letter A With Acute |
| Alt + 161 / Alt + 0237 | í   | Latin Small Letter I With Acute |
| Alt + 162 / Alt + 0243 | ó   | Latin Small Letter O With Acute |
|     |     |     |
| Alt + 163 / Alt + 0250 | ú   | Latin Small Letter U With Acute |
| Alt + 164 / Alt + 0241 | ñ   | Latin Small Letter N With Tilde |
| Alt + 165 / Alt + 0209 | Ñ   | Latin Capital Letter N With Tilde |
| Alt + 0138 / Alt + 0352 | Š   | Latin Capital Letter S With Caron |
| Alt + 0140 / Alt + 0338 | Œ   | Latin Capital Ligature Oe |
| Alt + 0142 / Alt + 0381 | Ž   | Latin Capital Letter Z With Caron |
| Alt + 0154 / Alt + 0353 | š   | Latin Small Letter S With Caron |
|     |     |     |
| Alt + 0156 / Alt + 0339 | œ   | Latin Small Ligature Oe |
| Alt + 0158 / Alt + 0382 | ž   | Latin Small Letter Z With Caron |
| Alt + 0159 / Alt + 0376 | Ÿ   | Latin Capital Letter With Diaeresis |
| Alt + 0192 | À   | Latin Capital Letter A With Grave |
| Alt + 0193 | Á   | Latin Capital Letter A With Acute |
| Alt + 0194 | Â   | Latin Capital Letter A With Circumflex |
| Alt + 0195 | Ã   | Latin Capital Letter A With Tilde |
|     |     |     |
| Alt + 0200 | È   | Latin Capital Letter E With Grave |
| Alt + 0202 | Ê   | Latin Capital Letter E With Circumflex |
| Alt + 0203 | Ë   | Latin Capital Letter E With Diaeresis |
| Alt + 0204 | Ì   | Latin Capital Letter I With Grave |
| Alt + 0205 | Í   | Latin Capital Letter I With Acute |
| Alt + 0206 | Î   | Latin Capital Letter I With Circumflex |
| Alt + 0207 | Ï   | Latin Capital Letter I With Diaeresis |
|     |     |     |
| Alt + 0208 | Ð   | Latin Capital Letter Eth |
| Alt + 0210 | Ò   | Latin Capital Letter O With Grave |
| Alt + 0211 | Ó   | Latin Capital Letter O With Acute |
| Alt + 0212 | Ô   | Latin Capital Letter O With Circumflex |
| Alt + 0213 | Õ   | Latin Capital Letter O With Tilde |
| Alt + 0216 | Ø   | Latin Capital Letter O With Stroke |
| Alt + 0217 | Ù   | Latin Capital Letter U With Grave |
|     |     |     |
| Alt + 0218 | Ú   | Latin Capital Letter U With Acute |
| Alt + 0219 | Û   | Latin Capital Letter U With Circumflex |
| Alt + 0221 | Ý   | Latin Capital Letter Y With Acute |
| Alt + 0222 | Þ   | Latin Capital Letter Thorn |
| Alt + 0227 | ã   | Latin Small Letter A With Tilde |
| Alt + 0240 | ð   | Latin Small Letter Eth |
| Alt + 0245 | õ   | Latin Small Letter O With Tilde |
|     |     |     |
| Alt + 0248 | ø   | Latin Small Letter O With Slash |
| Alt + 0253 | ý   | Latin Small Letter Y With Acute |
| Alt + 0254 | þ   | Latin Small Letter Thorn |
| Alt + 0256 | Ā   | Latin Capital Letter A With Macron |
| Alt + 0257 | ā   | Latin Small Letter A With Macron |
| Alt + 0258 | Ă   | Latin Capital Letter A With Caron |
| Alt + 0259 | ă   | Latin Small Letter A With Caron |
|     |     |     |
| Alt + 0260 | Ą   | Latin Capital Letter A With Ogonek |
| Alt + 0261 | ą   | Latin Small Letter A With Ogonek |
| Alt + 0262 | Ć   | Latin Capital Letter C With Acute |
| Alt + 0263 | ć   | Latin Small Letter C With Acute |
| Alt + 0264 | Ĉ   | Latin Capital Letter C With Circumflex |
| Alt + 0265 | ĉ   | Latin Small Letter C With Circumflex |
| Alt + 0266 | Ċ   | Latin Capital Letter C With Dot Above |
|     |     |     |
| Alt + 0267 | ċ   | Latin Small Letter C With Dot Above |
| Alt + 0268 | Č   | Latin Capital Letter C With Caron |
| Alt + 0269 | č   | Latin Small Letter C With Caron |
| Alt + 0270 | Ď   | Latin Capital Letter D With Caron |
| Alt + 0271 | ď   | Latin Small Letter D With Caron |
| Alt + 0272 | Đ   | Latin Capital Letter D With Stroke |
| Alt + 0273 | đ   | Latin Small Letter D With Stroke |
|     |     |     |
| Alt + 0274 | Ē   | Latin Capital Letter E With Stroke |
| Alt + 0275 | ē   | Latin Small Letter E With Stroke |
| Alt + 0276 | Ĕ   | Latin Capital Letter E With Breve |
| Alt + 0277 | ĕ   | Latin Small Letter E With Breve |
| Alt + 0278 | Ė   | Latin Capital Letter E With Dot Above |
| Alt + 0279 | ė   | Latin Small Letter E With Dot Above |
| Alt + 0280 | Ę   | Latin Capital Letter E With Ogonek |
|     |     |     |
| Alt + 0281 | ę   | Latin Small Letter E With Ogonek |
| Alt + 0282 | Ě   | Latin Capital Letter E With Breve |
| Alt + 0283 | ě   | Latin Small Letter E With Breve |
| Alt + 0284 | Ĝ   | Latin Capital Letter G With Circumflex |
| Alt + 0285 | ĝ   | Latin Small Letter G With Circumflex |
| Alt + 0286 | Ğ   | Latin Capital Letter G With Breve |
| Alt + 0287 | ğ   | Latin Small Letter G With Breve |
|     |     |     |
| Alt + 0288 | Ġ   | Latin Capital Letter G With Dot Above |
| Alt + 0289 | ġ   | Latin Small Letter G With Dot Above |
| Alt + 0290 | Ģ   | Latin Capital Letter G With Cedilla |
| Alt + 0291 | ģ   | Latin Small Letter G With Cedilla |
| Alt + 0292 | Ĥ   | Latin Capital Letter H With Circumflex |
| Alt + 0293 | ĥ   | Latin Small Letter H With Circumflex |
| Alt + 0294 | Ħ   | Latin Capital Letter H With Stroke |
|     |     |     |
| Alt + 0295 | ħ   | Latin Small Letter H With Stroke |
| Alt + 0296 | Ĩ   | Latin Capital Letter I With Tilde |
| Alt + 0297 | ĩ   | Latin Small Letter I With Tilde |
| Alt + 0298 | Ī   | Latin Capital Letter I With Macron |
| Alt + 0299 | ī   | Latin Small Letter I With Macron |
| Alt + 0300 | Ĭ   | Latin Capital Letter I With Breve |
| Alt + 0301 | ĭ   | Latin Small Letter I With Breve |
|     |     |     |
| Alt + 0302 | Į   | Latin Capital Letter I With Ogonek |
| Alt + 0303 | į   | Latin Small Letter I With Ogonek |
| Alt + 0304 | İ   | Latin Capital Letter I With Dot Above |
| Alt + 0305 | ı   | Latin Small Letter Dotless I |
| Alt + 0306 | Ĳ   | Latin Capital Ligature Ij |
| Alt + 0307 | ĳ   | Latin Small Ligature Ij |
| Alt + 0308 | Ĵ   | Latin Capital Letter J With Circumflex |
|     |     |     |
| Alt + 0309 | ĵ   | Latin Small Letter J With Circumflex |
| Alt + 0310 | Ķ   | Latin Capital Letter K With Cedilla |
| Alt + 0311 | ķ   | Latin Small Letter K With Cedilla |
| Alt + 0312 | ĸ   | Latin Small Letter Kra |
| Alt + 0313 | Ĺ   | Latin Capital Letter L With Acute |
| Alt + 0314 | ĺ   | Latin Small Letter L With Acute |
| Alt + 0315 | Ļ   | Latin Capital Letter L With Cedilla |
|     |     |     |
| Alt + 0316 | ļ   | Latin Small Letter L With Cedilla |
| Alt + 0317 | Ľ   | Latin Capital Letter L With Caron |
| Alt + 0318 | ľ   | Latin Small Letter L With Caron |
| Alt + 0319 | Ŀ   | Latin Capital Letter L With Middle Dot |
| Alt + 0320 | ŀ   | Latin Small Letter L With Middle Dot |
| Alt + 0321 | Ł   | Latin Capital Letter L With Stroke |
| Alt + 0322 | ł   | Latin Small Letter L With Stroke |
|     |     |     |
| Alt + 0323 | Ń   | Latin Capital Letter N With Acute |
| Alt + 0324 | ń   | Latin Small Letter N With Acute |
| Alt + 0325 | Ņ   | Latin Capital Letter N With Cedilla |
| Alt + 0326 | ņ   | Latin Small Letter N With Cedilla |
| Alt + 0327 | Ň   | Latin Capital Letter N With Caron |
| Alt + 0328 | ň   | Latin Small Letter N With Caron |
| Alt + 0329 | ŉ   | Latin Small Letter N Preceded by an Apostrophe |
|     |     |     |
| Alt + 0330 | Ŋ   | Latin Capital Letter Eng |
| Alt + 0331 | ŋ   | Latin Small Letter Eng |
| Alt + 0332 | Ō   | Latin Capital Letter O With Macron |
| Alt + 0333 | ō   | Latin Small Letter O With Macron |
| Alt + 0334 | Ŏ   | Latin Capital Letter O With Breve |
| Alt + 0335 | ŏ   | Latin Small Letter O With Breve |
| Alt + 0336 | Ő   | Latin Capital Letter O With Double Acute |
|     |     |     |
| Alt + 0337 | ő   | Latin Small Letter O With Double Acute |
| Alt + 0340 | Ŕ   | Latin Capital Letter R With Acute |
| Alt + 0341 | ŕ   | Latin Small Letter R With Acute |
| Alt + 0342 | Ŗ   | Latin Capital Letter R With Cedilla |
| Alt + 0343 | ŗ   | Latin Small Letter R With Cedilla |
| Alt + 0344 | Ř   | Latin Capital Letter R With Caron |
| Alt + 0345 | ř   | Latin Small Letter R With Caron |
|     |     |     |
| Alt + 0346 | Ś   | Latin Capital Letter S With Acute |
| Alt + 0347 | ś   | Latin Small Letter S With Acute |
| Alt + 0348 | Ŝ   | Latin Capital Letter S With Circumflex |
| Alt + 0349 | ŝ   | Latin Small Letter S With Circumflex |
| Alt + 0350 | Ş   | Latin Capital Letter S With Cedilla |
| Alt + 0351 | ş   | Latin Small Letter S With Cedilla |
| Alt + 0354 | Ţ   | Latin Capital Letter T With Cedilla |
|     |     |     |
| Alt + 0355 | ţ   | Latin Small Letter T With Cedilla |
| Alt + 0356 | Ť   | Latin Capital Letter T With Caron |
| Alt + 0357 | ť   | Latin Small Letter T With Caron |
| Alt + 0358 | Ŧ   | Latin Capital Letter T With Stroke |
| Alt + 0359 | ŧ   | Latin Small Letter T With Stroke |
| Alt + 0360 | Ũ   | Latin Capital Letter U With Tilde |
| Alt + 0361 | ũ   | Latin Small Letter U With Tilde |
|     |     |     |
| Alt + 0362 | Ū   | Latin Capital Letter U With Macron |
| Alt + 0363 | ū   | Latin Small Letter U With Macron |
| Alt + 0364 | Ŭ   | Latin Capital Letter U With Breve |
| Alt + 0365 | ŭ   | Latin Small Letter U With Breve |
| Alt + 0366 | Ů   | Latin Capital Letter U With Ring Above |
| Alt + 0367 | ů   | Latin Small Letter U With Ring Above |
| Alt + 0368 | Ű   | Latin Capital Letter With Double Acute |
|     |     |     |
| Alt + 0369 | ű   | Latin Small Letter U With Double Acute |
| Alt + 0370 | Ų   | Latin Capital Letter U With Ogonek |
| Alt + 0371 | ų   | Latin Small Letter U With Ogonek |
| Alt + 0372 | Ŵ   | Latin Capital Letter W With Circumflex |
| Alt + 0373 | ŵ   | Latin Small Letter W With Circumflex |
| Alt + 0374 | Ŷ   | Latin Capital Letter Y With Circumflex |
| Alt + 0375 | ŷ   | Latin Small Letter Y With Circumflex |
|     |     |     |
| Alt + 0377 | Ź   | Latin Capital Letter Z With Acute |
| Alt + 0378 | ź   | Latin Small Letter Z With Acute |
| Alt + 0379 | Ż   | Latin Capital Letter Z With Dot Above |
| Alt + 0380 | ż   | Latin Small Letter Z With Dot Above |
| **Logic Signs** |     |     |
| Alt + 169 | ⌐   | Reversed Not Sign |
| Alt + 170 / Alt + 0172 | ¬   | Not Sign |
|     |     |     |
| **Greek Characters** |     |     |
| Alt + 224 | α   | Greek Small Letter Alpha |
| Alt + 225 / Alt + 0223 | ß   | Greek Small Letter Beta |
| Alt + 226 | Γ   | Greek Capital Letter Gamma |
| Alt + 227 | π   | Greek Small Letter Pi |
| Alt + 228 | Σ   | Greek Capital Letter Sigma |
| Alt + 229 | σ   | Greek Small Letter Sigma |
|     |     |     |
| Alt + 230 / Alt + 0181 | µ   | Greek Small Letter Mu |
| Alt + 231 | τ   | Greek Small Letter Tau |
| Alt + 232 | Φ   | Greek Capital Letter Phi |
| Alt + 233 | Θ   | Greek Capital Letter Theta |
| Alt + 234 | Ω   | Greek Capital Letter Omega |
| Alt + 235 | δ   | Greek Small Letter Delta |
| Alt + 237 | φ   | Greek Small Letter Phi |
| Alt + 238 | ε   | Greek Small Letter Epsilon |



