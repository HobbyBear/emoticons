## Parse text emoticons and replace them by graphics.

### Get the api

    // Within commonjs
    var emoticons = require('emoticons');

    // Within jquery
    $.emoticons;

    // From global
    window.emoticons;

### emoticons.define(data:Object)

Define a set of emoticons. See the format in skype.json. First code in the codes array will be used as primary one.

Example:

    emoticons.define(
        "smile": {
            "title": "Smile",
            "codes": [":)", ":=)", ":-)"]
        }
    );

### emoticons.replace(text:String, [fn:Function])

Replace text emoticons by html elements which can be then styled with graphics.

Example:

    emoticons.replace(':)');

    If you don't like the generated html, pass your own template builder function.

    emoticons.replace(':)', function(name, code) {
        return '<div>' + code + '</div>';
    });

### emoticons.toString([fn:Function])

Get html string with all primary emoticons in order to display an overview.

### emoticons.tpl(name:String, code:String)

If you want to overwrite the default template builder function.

Example:

    emoticons.tpl = function(name, code) {
        return '<div>' + code + '</div>';
    };


## External components

Thanks to Chris Messina for making this overview http://factoryjoe.com/projects/emoticons

Skype icons included in the package have special license, which is like BSD but without permission to modify them. See LICENSE file for original blog post.





