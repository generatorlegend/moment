# Formatting and Parsing Dates and Times with Moment.js

Moment.js provides powerful tools for formatting and parsing dates and times. This guide will explain how to use these features effectively in your projects.

## Formatting Dates and Times

### Basic Formatting

To format a Moment object, use the `format()` method:

```javascript
const now = moment();
console.log(now.format('YYYY-MM-DD HH:mm:ss')); // Output: 2023-04-20 14:30:00
```

### Custom Format Strings

Moment.js uses tokens to create custom format strings. Here are some common tokens:

- `YYYY`: 4-digit year
- `MM`: 2-digit month (01-12)
- `DD`: 2-digit day of month (01-31)
- `HH`: 2-digit hour (00-23)
- `mm`: 2-digit minute (00-59)
- `ss`: 2-digit second (00-59)

For a complete list of tokens, refer to the `formattingTokens` regular expression in the `src/lib/format/format.js` file.

### Localized Formatting

Moment.js supports localized formatting. Use the `locale()` method to set the desired locale:

```javascript
moment.locale('fr');
const date = moment('2023-04-20');
console.log(date.format('LL')); // Output: 20 avril 2023
```

## Parsing Dates and Times

### Basic Parsing

To parse a date string, pass it to the `moment()` function:

```javascript
const date = moment('2023-04-20');
console.log(date.format('YYYY-MM-DD')); // Output: 2023-04-20
```

### Parsing with Custom Formats

For non-standard date formats, specify the format string:

```javascript
const date = moment('20/04/2023', 'DD/MM/YYYY');
console.log(date.format('YYYY-MM-DD')); // Output: 2023-04-20
```

### Parsing Various Date String Formats

Moment.js can parse a wide range of date string formats. The `src/lib/parse/regex.js` file contains regular expressions for matching different date and time patterns. For example:

- `match1to2`: Matches 1 or 2 digits (e.g., day or month)
- `match4`: Matches exactly 4 digits (e.g., year)
- `matchWord`: Matches words (e.g., month names)

When parsing, Moment.js uses these regular expressions to interpret the input string correctly.

## Advanced Formatting and Parsing

### Custom Token Functions

You can add custom formatting tokens using the `addFormatToken()` function:

```javascript
import { addFormatToken } from 'moment/src/lib/format/format';

addFormatToken('Q', 0, 'Qo', function () {
    return Math.ceil((this.month() + 1) / 3);
});

console.log(moment().format('YYYY [Q]Q')); // Output: 2023 Q2
```

### Expanding Format Strings

The `expandFormat()` function in `src/lib/format/format.js` is used internally to expand shorthand formats into their full representation. For example, it can expand 'LT' into the locale's long time format.

## Best Practices

1. Always validate parsed dates using the `isValid()` method.
2. Use ISO 8601 format (YYYY-MM-DD) for consistent date representation across different locales.
3. When working with user input, always specify the expected format to avoid ambiguity.
4. Use localized formatting when displaying dates to end-users.

By understanding these formatting and parsing capabilities, you can effectively work with dates and times in your Moment.js projects.