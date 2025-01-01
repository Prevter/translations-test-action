<div align="center">
   <h1 align="center">Eclipse Translations</h1>
   <p align="center">
        A repository for Eclipse Menu translations.
   </p>
</div>
<div align="center">

</div>

## How to contribute
1. Fork this repository
2. Add or edit translations in the `translations` folder (see [adding languages](#adding-languages) for more information)
3. Create a pull request
4. Wait for your pull request to be reviewed and merged

## Adding languages
Language files are stored as JSON files, that contain metadata and key-value pairs for each translation.

Metadata is stored at the top of the file, and contains the following fields:
```json5
{
    "language-name": "English",    // The name of the language in English
    "language-code": "en",         // The language code (ISO 639-1)
    "language-native": "English",  // The name of the language in its native language
    "language-charset": "default", // The character set of the language
    "language-fallback": "en",     // The fallback language code (defaults to English)
    
    // ... translations go here
}
```

`language-name`, `language-code` and `language-native` are required and should be self-explanatory.

`language-charset` is optional and defaults to `default`.
If the language uses a different character set, you can specify it here.
Supported values are:
- `default`
- `greek`
- `korean`
- `japanese`
- `chinese-full`
- `chinese-simplified`
- `cyrillic`
- `thai`
- `vietnamese`

This will tell Eclipse which font to use for the language.

`language-fallback` is optional and defaults to `en`.
If a translation is missing for a key in the current language,
Eclipse will fall back to the specified language.
You can use this to avoid duplicating translations for similar languages (e.g. `es` and `pt`).

> Note: this field is not recursive, so if a translation is missing in the fallback language, it will not fall back further.