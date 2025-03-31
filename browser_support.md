# Browser Support for Moment.js

Moment.js is a widely used JavaScript library for parsing, validating, manipulating, and formatting dates. This document outlines the browser support for Moment.js and provides guidance on how to use it in different environments.

## Supported Browsers

Moment.js is compatible with a wide range of browsers, including:

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Internet Explorer 11+
- iOS (latest)
- Android (latest)

## ECMAScript Support

Moment.js is written in ECMAScript 5 (ES5) and should work in any environment that supports ES5. This includes all modern browsers and Node.js environments.

## Older Browser Support

For older browsers that may not fully support ES5 features, you might need to include polyfills. Here are some recommendations:

1. For Internet Explorer 8 and below, consider using the es5-shim library.
2. If you're targeting very old browsers, you may also need to include a JSON polyfill.

## Using Moment.js in Different Environments

### Browser

To use Moment.js in a browser environment, include the script in your HTML file:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.30.1/moment.min.js"></script>
```

Then you can use Moment.js in your JavaScript code:

```javascript
var now = moment();
console.log(now.format('YYYY-MM-DD HH:mm:ss'));
```

### Node.js

To use Moment.js in a Node.js environment, first install it using npm:

```bash
npm install moment
```

Then you can require it in your JavaScript file:

```javascript
const moment = require('moment');
const now = moment();
console.log(now.format('YYYY-MM-DD HH:mm:ss'));
```

### AMD (Asynchronous Module Definition)

Moment.js also supports AMD loaders like RequireJS. You can use it like this:

```javascript
require(['moment'], function(moment) {
    var now = moment();
    console.log(now.format('YYYY-MM-DD HH:mm:ss'));
});
```

## Localization

Moment.js supports localization out of the box. When using in a browser environment, you'll need to include the locale files you want to use. In Node.js, all locales are included by default.

### Browser Example:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.30.1/moment.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.30.1/locale/fr.js"></script>
<script>
    moment.locale('fr');
    console.log(moment().format('LLLL'));
</script>
```

### Node.js Example:

```javascript
const moment = require('moment');
require('moment/locale/fr');

moment.locale('fr');
console.log(moment().format('LLLL'));
```

## Performance Considerations

While Moment.js is highly versatile, it can be quite large (especially when including multiple locales). For performance-critical applications or when targeting older or low-powered devices, consider using a lighter alternative or only including the features you need.

## Conclusion

Moment.js provides excellent browser support and can be easily integrated into various JavaScript environments. By following the guidelines in this document, you should be able to use Moment.js effectively across different browsers and platforms.

For more detailed information on using Moment.js, refer to the [official documentation](https://momentjs.com/docs/).