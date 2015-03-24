# handlebars.filter
    
    {{filter str filtername}}

Content filtering helper for [Handlebars](http://handlebarsjs.com)

### Version

1.0.0

### Installation

    npm install handlebars.filter

### Registering the helper

    var Handlebars = require("handlebars");
    var Filter = require("handlebars.filter");
    Filter.registerHelper(Handlebars);

### Using the helper

Apply a filter to content

    {{filter str filtername}}

Apply a filter to captured content

    {{#filter filtername}}{{str}}{{/filter}}

Apply chained filters to content

    {{filter str filter1 filter2}}

### Using the filters

*Assuming a context of `{str: "the FOX and the hoUnd"}`*

Apply lowercase filter

    {{filter str "lowercase"}}                  → «the fox and the hound»

Apply uppercase filter

    {{filter str "uppercase"}}                  → «THE FOX AND THE HOUND»

Apply capitalize filter

    {{filter str "capitalize"}}                 → «The FOX And The HoUnd»

Apply capitalize filter overriding any existing casing

    {{filter str "capitalize" respect=false}}   → «The Fox And The Hound»

Apply titlecase filter

    {{filter str "titlecase"}}                  → «The Fox and the Hound»

Apply markdown filter

    {{filter "## Hello *World*!" "markdown"}}   → «<h2>Hello <em>World</em>!</h2>»

### Additional methods

#### Filter.registerFilter

    Filter.registerFilter(name, fn);

Register a named filter method

#### Filter.registerHelper

    Filter.registerHelper(handlebars);

Register Filter helper with Handlebars

### Tests

To run the tests, cd to the handlebars.filter directory

    npm install && npm test
### Unlicense

handlebars.filter is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or distribute this software, either in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means.

In jurisdictions that recognize copyright laws, the author or authors of this software dedicate any and all copyright interest in the software to the public domain. We make this dedication for the benefit of the public at large and to the detriment of our heirs and successors. We intend this dedication to be an overt act of relinquishment in perpetuity of all present and future rights to this software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to http://unlicense.org