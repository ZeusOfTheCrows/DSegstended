* in fontforge, many characters are references to other glyphs
	* here is the hierarchy diagram for DSeg14:

````

┌─LATIN ─► LATIN ACCENTED (inc. Ð)
│   │
│   ▼                    ┌► CYRILLIC ACCENTED ─┐
│ CYRILLIC ─► CYRILLIC* ─┤                     ▼
│   │                    └► cyrillic ───► cyrillic accented
├───┤ ┌──────────────────────────────────────────┐
│   │ │ *Б ─► В, Е ─► Ё, И ─► Й, Ш ─► Щ          │
│   │ └──────────────────────────────────────────┘
│   ▼
│ GREEK ─► ø
│       ┌───────────────────────────────────────────────────┐
│       │(latin Z ─► ZETA, latin T ─► TAU,                  │
│       │latin H ─► ETA, latin I ─► IOTA, latin N ─► NU,    │
│       │# → majuscule SIGMA NULL, latin z → zeta,          │
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
  │/ ─► norwegian Ø, | ─► cyrillic Ф, # ─► Sigma null│
  │                                                  │
  │- ─► fullwidth 7, FULLWIDTH Z, mu ─► micro sign   │
  │- ─► yen sign ¥, - ─► tilde ~, soft hyphen        │
  └──────────────────────────────────────────────────┘
 

````

