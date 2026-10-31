<h1 align="center">
    Unidecode
</h1>

<p align="center">
     <i>Unicode -> ASCII converter package for Arturo</i> 
     <br><br>
     <img src="https://img.shields.io/github/license/drkameleon/unidecode.art?style=for-the-badge">
    <a href="https://github.com/arturo-lang/arturo" style="text-decoration: none; display: inline-block;"><img src="https://img.shields.io/badge/language-Arturo-6A156B.svg?style=for-the-badge" alt="Language"/></a>
    <a href="https://github.com/drkameleon/unidecode.art/actions/workflows/ci.yml" style="text-decoration: none; display: inline-block;"><img src="https://img.shields.io/github/actions/workflow/status/drkameleon/unidecode.art/ci.yml?branch=main&label=tests&style=for-the-badge" alt="Tests"/></a>
</p>

<hr/>

### What does this package do?

Let's say you have a Unicode string, with different characters, in different languages, e.g. characters with accents, in cyrillic, Mandarin Chinese, etc and - for whatever reason - want to have a *close approximation* to what it would be like using only ASCII characters, then this package is for you.

> [!TIP]
> The package has been based on [Nim's implementation](https://nim-lang.org/docs/unidecode.html#unidecode%2Cstring), of the same name - which in turn has been based on Python's [Unidecode](https://pypi.org/project/Unidecode/) module by Tomaž Šolc, itself a port of Perl's [Text::Unidecode](https://metacpan.org/pod/Text::Unidecode) by Sean M. Burke - and that's where the transliteration data (`src/data.txt`) comes from.

### How do I use it?

Simply `import` it and use the included `unidecode` function:

```arturo
import "unidecode"!

print unidecode "доброе утро!"
; will print:
; dobroe utro!
```

> [!IMPORTANT]
> The package cannot possibly guarantee that the output will be "accurate", nor is it 100% easy to say what would be accurate in every possible case - it's an *approximate* Unicode -> ASCII transformation. So, if you need a better solution for your specific needs, you might be better off writing a custom solution yourself!

### Limitations

- Only characters within the Basic Multilingual Plane (U+0000 to U+FFFF) are supported - anything beyond that (e.g. emoji, rare CJK ideographs, mathematical alphanumeric symbols, etc) is silently removed
- Han characters are always transliterated using their Mandarin reading - regardless of whether they are Chinese hanzi, Japanese kanji or Korean hanja (e.g. `日本` becomes `Ri Ben`, not `Nihon`)

<hr/>

### License

MIT License

Copyright (c) 2026 Yanis Zafirópulos

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

The transliteration data (`src/data.txt`) has been derived from Nim's `unidecode`
module, itself based on Python's Unidecode by Tomaž Šolc and Perl's
Text::Unidecode by Sean M. Burke.
