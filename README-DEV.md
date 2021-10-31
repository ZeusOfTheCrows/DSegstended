# useful miscellany for extending DSeg

/!\ i didn't create DSeg, so i'm only documenting things i've found - i can't guarantee it's comprehensive or correct

### generic

* the null character in the middle of the greek alphabet is due to greek having a final form for sigma
	* theoretically, it shouldn't matter what glyph is there - it should never be seen
	* i use it as storage so i can copy the filled char easily

### DSeg14:

* in fontforge, many characters are references to other glyphs
* however, all characters are references to 17 fragments
  * these fragments are all stored in private use area uEE00—uEE11
  	* /!\ changing uEE0F may not cascade properly
  	* this is my screw-up, but i can't be arsed to fix it unless i need to
* apart from those fragments, the other characters have cascading hierarchy
  * here is the hierarchy diagram for DSeg14:

````

┌─LATIN ─► LATIN ACCENTED (inc. Ð)
│   │
│   ▼                    ┌► CYRILLIC ACCENTED ─┐
│ CYRILLIC ─► CYRILLIC* ─┤                     ▼
│   │                    └► cyrillic ───► cyrillic accented
├───┤ ┌──────────────────────────────────────────┐
│   │ │ *Б ─► В, Е ─► Ё, И ─► Й, О ─► Ф, Ш ─► Щ  │
│   │ └──────────────────────────────────────────┘
│   ▼
│ GREEK ─► ø
│       ┌───────────────────────────────────────────────────┐
│       │(latin Z ─► ZETA, latin T ─► TAU,                  │
│       │latin H ─► ETA, latin I ─► IOTA, latin N ─► NU,    │
│       │latin z → zeta,                                    │
│       │latin o ─► omicron, latin p ─► rho, latin x ─► chi)│
│       └───────────────────────────────────────────────────┘
│
│  latin  ─► latin accented (inc.ð)
│    ├───►greek (zeta, omicron, rho, chi)
│    ▼
│  latin fullwidth
│
└► LATIN FULLWIDTH

   punctuation ─► fullwidth punctuation

  ┌──────────────────────────────────────────────────┐
  │/ ─► norwegian Ø, mu ─► micro sign                │
  │- ─► yen sign ¥, - ─► tilde ~, soft hyphen        │
  └──────────────────────────────────────────────────┘
 

````

