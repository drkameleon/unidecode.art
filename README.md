<h1 align="center">
    Unidecode
</h1>

<p align="center">
     <i>Unicode -> ASCII converter package for  Arturo</i> 
</p>

<hr/>

### What does this package do?

Let's say you have a Unicode string, with different characters, in different languages, e.g. characters with accents, in cyrillic, Mandarin Chinese, etc and - for whatever reason - want to have a *close approximation* to what it would be like using only ASCII characters, then this package is for you.

> [!TIP]
> The package has been based on [Nim's implementation](https://nim-lang.org/docs/unidecode.html#unidecode%2Cstring), of the same name - which in turn has been based on the Python's Unidecode module by Tomaz Solc.

### How do I use it?

Simply `import` it and use the included `unidecode` function:

```arturo
import "unidecode"!

print unidecode "доброе утро!"
; will print:
; dobroe utro!
```

> [!IMPORTANT]
> The package cannot possibly guarantee that the output will be "accurate", not is it 100% easy to say what would be accurate in every possible case - it's an *approximate* Unicode -> ASCII transformation. So, if you need a better solution for your specific needs, you might be better of writing a custom solution yourself!

<hr/>

### License

MIT License

Copyright (c) 2024 Yanis Zafirópulos

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