# transliterate

> Convert Unicode characters to Latin characters using [transliteration](https://en.wikipedia.org/wiki/Transliteration)

Can be useful for [slugification](https://github.com/sindresorhus/slugify) purposes and other times you cannot use Unicode.

## Install

```
$ npm install @sindresorhus/transliterate
```

## Usage

```js
import transliterate from '@sindresorhus/transliterate';

transliterate('Fußgängerübergänge');
//=> 'Fussgaengeruebergaenge'

transliterate('Я люблю единорогов');
//=> 'Ya lyublyu edinorogov'

transliterate('أنا أحب حيدات');
//=> 'ana ahb hydat'

transliterate('tôi yêu những chú kỳ lân');
//=> 'toi yeu nhung chu ky lan'
```

## API

### transliterate(string, options?)

#### string

Type: `string`

String to transliterate.

#### options

Type: `object`

##### customReplacements

Type: `Array<string[]>`\
Default: `[]`

Add your own custom replacements.

The replacements are run on the original string before any other transformations.

This only overrides a default replacement if you set an item with the same key.

```js
import transliterate from '@sindresorhus/transliterate';

transliterate('Я люблю единорогов', {
	customReplacements: [
		['единорогов', '🦄']
	]
})
//=> 'Ya lyublyu 🦄'
```

## Supported languages

Most major languages are supported. Some of the languages are disabled (commented out) by default in `replacements.js` for conflicting with other languages.

This includes special handling for:

- Arabic
- Armenian
- Czech
- Danish (disabled by default)
- Dhivehi
- Georgian
- German (umlauts)
- Greek
- Hungarian (disabled by default)
- Latin
- Latvian
- Lithuanian
- Macedonian
- Pashto
- Persian
- Polish
- Romanian
- Russian
- Serbian (disabled by default)
- Slovak (disabled by default)
- Swedish/Finnish (disabled by default)
- Turkish
- Ukrainian
- Urdu
- Vietnamese

However, Chinese is [currently not supported](https://github.com/sindresorhus/transliterate/issues/1).

## Related

- [slugify](https://github.com/sindresorhus/slugify) - Slugify a string
