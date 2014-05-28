# node-unicode-data [![Build status](https://travis-ci.org/mathiasbynens/node-unicode-data.svg?branch=master)](https://travis-ci.org/mathiasbynens/node-unicode-data) [![Dependency status](https://gemnasium.com/mathiasbynens/node-unicode-data.svg)](https://gemnasium.com/mathiasbynens/node-unicode-data)

JavaScript-compatible Unicode data generator. Arrays of code points, arrays of symbols, and regular expressions for every Unicode version’s categories, scripts, blocks, bidi data, and other properties — neatly packaged into a separate npm package per Unicode version.

## Using the data in your scripts

To use the generated data, simply install one of [the npm modules generated by this script](https://npmjs.org/browse/keyword/unicode-data). Separate packages are available for each Unicode version. This allows you to do stuff like:

```js
// Get an array of all code points with the `White_Space` property:
var codePoints = require('unicode-6.3.0/properties/White_Space/code-points');
// Get an array of strings (containing one symbol each) in the `Lu` category:
var symbols = require('unicode-6.3.0/categories/Lu/symbols');
// Get a regular expression that matches any symbol in the `Aegean Numbers` block:
var regex = require('unicode-6.3.0/blocks/Aegean Numbers/regex');
// Get an array of all code points in the `Egyptian_Hieroglyphs` script:
var hieroglyphs = require('unicode-6.3.0/scripts/Egyptian_Hieroglyphs/code-points');
// Get the canonical category a given code point belongs to:
// (Note: U+0041 is LATIN CAPITAL LETTER A)
var category = require('unicode-6.3.0/categories')[ 0x41 ];
// Get an array of all code points with the `Bidi_LRE` bidi property:
var lre = require('unicode-6.3.0/bidi/LRE/code-points');
// Get the directionality of a given code point:
var directionality = require('unicode-6.3.0/bidi')[ 0x41 ];
// What glyph is the mirror image of `«` (U+00AB)?
var mirrored = require('unicode-6.3.0/bidi-mirroring')[ 0xAB ];
// Get a regular expression that matches all opening brackets:
var openingBrackets = require('unicode-6.3.0/bidi-brackets/Open/regex');
// …you get the idea.
```

For more information, see the README for the package you’re interested in. [Here’s the full list of npm packages generated by this script](https://npmjs.org/browse/keyword/unicode-data):

* [_unicode-1.1.5_](https://npmjs.org/package/unicode-1.1.5#readme)
* [_unicode-2.0.14_](https://npmjs.org/package/unicode-2.0.14#readme)
* [_unicode-2.1.2_](https://npmjs.org/package/unicode-2.1.2#readme)
* [_unicode-2.1.5_](https://npmjs.org/package/unicode-2.1.5#readme)
* [_unicode-2.1.8_](https://npmjs.org/package/unicode-2.1.8#readme)
* [_unicode-2.1.9_](https://npmjs.org/package/unicode-2.1.9#readme)
* [_unicode-3.0.0_](https://npmjs.org/package/unicode-3.0.0#readme)
* [_unicode-3.0.1_](https://npmjs.org/package/unicode-3.0.1#readme)
* [_unicode-3.1.0_](https://npmjs.org/package/unicode-3.1.0#readme)
* [_unicode-3.2.0_](https://npmjs.org/package/unicode-3.2.0#readme)
* [_unicode-4.0.0_](https://npmjs.org/package/unicode-4.0.0#readme)
* [_unicode-4.0.1_](https://npmjs.org/package/unicode-4.0.1#readme)
* [_unicode-4.1.0_](https://npmjs.org/package/unicode-4.1.0#readme)
* [_unicode-5.0.0_](https://npmjs.org/package/unicode-5.0.0#readme)
* [_unicode-5.1.0_](https://npmjs.org/package/unicode-5.1.0#readme)
* [_unicode-5.2.0_](https://npmjs.org/package/unicode-5.2.0#readme)
* [_unicode-6.0.0_](https://npmjs.org/package/unicode-6.0.0#readme)
* [_unicode-6.1.0_](https://npmjs.org/package/unicode-6.1.0#readme)
* [_unicode-6.2.0_](https://npmjs.org/package/unicode-6.2.0#readme)
* [_unicode-6.3.0_](https://npmjs.org/package/unicode-6.3.0#readme)

Note that these READMEs are auto-generated by this script, too – they describe all the data that is available for that particular Unicode version. To programmatically get this list of available categories, scripts, blocks, and properties for a given Unicode version, just `require` the main module for that version:

```js
> require('unicode-6.3.0');
{
  'properties': [
    'Any', 'Assigned', 'ASCII', 'White_Space', 'Bidi_Control', 'Join_Control',
    'Dash', 'Hyphen', 'Quotation_Mark', 'Terminal_Punctuation', 'Other_Math',
    'Hex_Digit', 'ASCII_Hex_Digit', 'Other_Alphabetic', 'Ideographic',
    'Diacritic', 'Extender', 'Other_Lowercase', 'Other_Uppercase',
    'Noncharacter_Code_Point', 'Other_Grapheme_Extend', 'IDS_Binary_Operator',
    'IDS_Trinary_Operator', 'Radical', 'Unified_Ideograph',
    'Other_Default_Ignorable_Code_Point', 'Deprecated', 'Soft_Dotted',
    'Logical_Order_Exception', 'Other_ID_Start', 'Other_ID_Continue', 'STerm',
    'Variation_Selector', 'Pattern_White_Space', 'Pattern_Syntax', 'Math',
    'Alphabetic', 'Lowercase', 'Uppercase', 'Cased', 'Case_Ignorable',
    'Changes_When_Lowercased', 'Changes_When_Uppercased',
    'Changes_When_Titlecased', 'Changes_When_Casefolded',
    'Changes_When_Casemapped', 'ID_Start', 'ID_Continue', 'XID_Start',
    'XID_Continue', 'Default_Ignorable_Code_Point', 'Grapheme_Extend',
    'Grapheme_Base', 'Grapheme_Link'
  ],
  'categories': [
    'Cc', 'C', 'Zs', 'Z', 'Po', 'P', 'Sc', 'S', 'Ps', 'Pe', 'Sm', 'Pd', 'Nd',
    'N', 'Lu', 'L', 'LC', 'Sk', 'Pc', 'Ll', 'So', 'Lo', 'Pi', 'Cf', 'No', 'Pf',
    'Lt', 'Lm', 'Mn', 'M', 'Cn', 'Me', 'Mc', 'Nl', 'Zl', 'Zp', 'Cs', 'Co'
  ],
  'scripts': [
    'Common', 'Latin', 'Greek', 'Cyrillic', 'Armenian', 'Hebrew', 'Arabic',
    'Syriac', 'Thaana', 'Devanagari', 'Bengali', 'Gurmukhi', 'Gujarati',
    'Oriya', 'Tamil', 'Telugu', 'Kannada', 'Malayalam', 'Sinhala', 'Thai',
    'Lao', 'Tibetan', 'Myanmar', 'Georgian', 'Hangul', 'Ethiopic', 'Cherokee',
    'Canadian_Aboriginal', 'Ogham', 'Runic', 'Khmer', 'Mongolian', 'Hiragana',
    'Katakana', 'Bopomofo', 'Han', 'Yi', 'Old_Italic', 'Gothic', 'Deseret',
    'Inherited', 'Tagalog', 'Hanunoo', 'Buhid', 'Tagbanwa', 'Limbu', 'Tai_Le',
    'Linear_B', 'Ugaritic', 'Shavian', 'Osmanya', 'Cypriot', 'Braille',
    'Buginese', 'Coptic', 'New_Tai_Lue', 'Glagolitic', 'Tifinagh',
    'Syloti_Nagri', 'Old_Persian', 'Kharoshthi', 'Balinese', 'Cuneiform',
    'Phoenician', 'Phags_Pa', 'Nko', 'Sundanese', 'Lepcha', 'Ol_Chiki', 'Vai',
    'Saurashtra', 'Kayah_Li', 'Rejang', 'Lycian', 'Carian', 'Lydian', 'Cham',
    'Tai_Tham', 'Tai_Viet', 'Avestan', 'Egyptian_Hieroglyphs', 'Samaritan',
    'Lisu', 'Bamum', 'Javanese', 'Meetei_Mayek', 'Imperial_Aramaic',
    'Old_South_Arabian', 'Inscriptional_Parthian', 'Inscriptional_Pahlavi',
    'Old_Turkic', 'Kaithi', 'Batak', 'Brahmi', 'Mandaic', 'Chakma',
    'Meroitic_Cursive', 'Meroitic_Hieroglyphs', 'Miao', 'Sharada',
    'Sora_Sompeng', 'Takri'
  ],
  'blocks': [
    'Basic Latin', 'Latin-1 Supplement', 'Latin Extended-A', 'Latin Extended-B',
    'IPA Extensions', 'Spacing Modifier Letters',
    'Combining Diacritical Marks', 'Greek and Coptic', 'Cyrillic',
    'Cyrillic Supplement', 'Armenian', 'Hebrew', 'Arabic', 'Syriac',
    'Arabic Supplement', 'Thaana', 'NKo', 'Samaritan', 'Mandaic',
    'Arabic Extended-A', 'Devanagari', 'Bengali', 'Gurmukhi', 'Gujarati',
    'Oriya', 'Tamil', 'Telugu', 'Kannada', 'Malayalam', 'Sinhala', 'Thai',
    'Lao', 'Tibetan', 'Myanmar', 'Georgian', 'Hangul Jamo', 'Ethiopic',
    'Ethiopic Supplement', 'Cherokee', 'Unified Canadian Aboriginal Syllabics',
    'Ogham', 'Runic', 'Tagalog', 'Hanunoo', 'Buhid', 'Tagbanwa', 'Khmer',
    'Mongolian', 'Unified Canadian Aboriginal Syllabics Extended', 'Limbu',
    'Tai Le', 'New Tai Lue', 'Khmer Symbols', 'Buginese', 'Tai Tham',
    'Balinese', 'Sundanese', 'Batak', 'Lepcha', 'Ol Chiki',
    'Sundanese Supplement', 'Vedic Extensions', 'Phonetic Extensions',
    'Phonetic Extensions Supplement', 'Combining Diacritical Marks Supplement',
    'Latin Extended Additional', 'Greek Extended', 'General Punctuation',
    'Superscripts and Subscripts', 'Currency Symbols',
    'Combining Diacritical Marks for Symbols', 'Letterlike Symbols',
    'Number Forms', 'Arrows', 'Mathematical Operators',
    'Miscellaneous Technical', 'Control Pictures',
    'Optical Character Recognition', 'Enclosed Alphanumerics',
    'Box Drawing', 'Block Elements', 'Geometric Shapes',
    'Miscellaneous Symbols', 'Dingbats', 'Miscellaneous Mathematical Symbols-A',
    'Supplemental Arrows-A', 'Braille Patterns', 'Supplemental Arrows-B',
    'Miscellaneous Mathematical Symbols-B', 'Supplemental Mathematical Operators',
    'Miscellaneous Symbols and Arrows', 'Glagolitic', 'Latin Extended-C',
    'Coptic', 'Georgian Supplement', 'Tifinagh', 'Ethiopic Extended',
    'Cyrillic Extended-A', 'Supplemental Punctuation', 'CJK Radicals Supplement',
    'Kangxi Radicals', 'Ideographic Description Characters',
    'CJK Symbols and Punctuation', 'Hiragana', 'Katakana', 'Bopomofo',
    'Hangul Compatibility Jamo', 'Kanbun', 'Bopomofo Extended', 'CJK Strokes',
    'Katakana Phonetic Extensions', 'Enclosed CJK Letters and Months',
    'CJK Compatibility', 'CJK Unified Ideographs Extension A',
    'Yijing Hexagram Symbols', 'CJK Unified Ideographs', 'Yi Syllables',
    'Yi Radicals', 'Lisu', 'Vai', 'Cyrillic Extended-B', 'Bamum',
    'Modifier Tone Letters', 'Latin Extended-D', 'Syloti Nagri',
    'Common Indic Number Forms', 'Phags-pa', 'Saurashtra', 'Devanagari Extended',
    'Kayah Li', 'Rejang', 'Hangul Jamo Extended-A', 'Javanese', 'Cham',
    'Myanmar Extended-A', 'Tai Viet', 'Meetei Mayek Extensions',
    'Ethiopic Extended-A', 'Meetei Mayek', 'Hangul Syllables',
    'Hangul Jamo Extended-B', 'High Surrogates', 'High Private Use Surrogates',
    'Low Surrogates', 'Private Use Area', 'CJK Compatibility Ideographs',
    'Alphabetic Presentation Forms', 'Arabic Presentation Forms-A',
    'Variation Selectors', 'Vertical Forms', 'Combining Half Marks',
    'CJK Compatibility Forms', 'Small Form Variants',
    'Arabic Presentation Forms-B', 'Halfwidth and Fullwidth Forms', 'Specials',
    'Linear B Syllabary', 'Linear B Ideograms', 'Aegean Numbers',
    'Ancient Greek Numbers', 'Ancient Symbols', 'Phaistos Disc', 'Lycian',
    'Carian', 'Old Italic', 'Gothic', 'Ugaritic', 'Old Persian', 'Deseret',
    'Shavian', 'Osmanya', 'Cypriot Syllabary', 'Imperial Aramaic', 'Phoenician',
    'Lydian', 'Meroitic Hieroglyphs', 'Meroitic Cursive', 'Kharoshthi',
    'Old South Arabian', 'Avestan', 'Inscriptional Parthian',
    'Inscriptional Pahlavi', 'Old Turkic', 'Rumi Numeral Symbols',
    'Brahmi', 'Kaithi', 'Sora Sompeng', 'Chakma', 'Sharada', 'Takri',
    'Cuneiform', 'Cuneiform Numbers and Punctuation', 'Egyptian Hieroglyphs',
    'Bamum Supplement', 'Miao', 'Kana Supplement', 'Byzantine Musical Symbols',
    'Musical Symbols', 'Ancient Greek Musical Notation', 'Tai Xuan Jing Symbols',
    'Counting Rod Numerals', 'Mathematical Alphanumeric Symbols',
    'Arabic Mathematical Alphabetic Symbols', 'Mahjong Tiles',
    'Domino Tiles', 'Playing Cards', 'Enclosed Alphanumeric Supplement',
    'Enclosed Ideographic Supplement', 'Miscellaneous Symbols And Pictographs',
    'Emoticons', 'Transport And Map Symbols', 'Alchemical Symbols',
    'CJK Unified Ideographs Extension B', 'CJK Unified Ideographs Extension C',
    'CJK Unified Ideographs Extension D',
    'CJK Compatibility Ideographs Supplement', 'Tags',
    'Variation Selectors Supplement', 'Supplementary Private Use Area-A',
    'Supplementary Private Use Area-B'
  ],
  'case-folding': [
    'C', 'T', 'F', 'S'
  ],
  'bidi': [
    'AL', 'B', 'CS', 'ES', 'FSI', 'LRE', 'LRO', 'ON', ' PDI', 'RLE', 'RLO',
    'WS', 'AN', 'BN', 'EN', 'ET', 'L', 'LRI', 'NSM', 'PDF', 'R', 'RLI', 'S'
  ],
  'bidi-mirroring': [],
  'bidi-brackets': [
    'Open', 'Close'
  ]
}
```

## Generating the data

`npm run-script download` (re-)downloads the Unicode source files for all the Unicode versions defined in `data/resources.js`, saving them in the `data` folder.

`npm run-script generate` generates data for categories, scripts, blocks, and properties for all the Unicode versions defined in `data/resources.js`. This may take a few minutes… In total, roughly 1.5 GB of data is generated. The regular expressions are generated using [Regenerate](http://mths.be/regenerate), and [Punycode.js](http://mths.be/punycode) is used to convert code point arrays into arrays of symbols.

## Testing

`npm test` generates the data for the oldest and latest available Unicode version. This is a good way to test changes to the generator scripts before running `npm run-script generate`.

`npm run-script cover` generates [the code coverage report](http://rawgithub.com/mathiasbynens/node-unicode-data/master/coverage/index.html).

## Author

| [![twitter/mathias](https://gravatar.com/avatar/24e08a9ea84deb17ae121074d0f17125?s=70)](https://twitter.com/mathias "Follow @mathias on Twitter") |
|---|
| [Mathias Bynens](http://mathiasbynens.be/) |

## License

This module is available under the [MIT](http://mths.be/mit) license.
