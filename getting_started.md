# Getting Started with Moment.js

Moment.js is a popular JavaScript library for parsing, validating, manipulating, and formatting dates and times. This guide will help you get started with Moment.js in your project.

## Installation

You can install Moment.js using npm:

```bash
npm install moment
```

Or include it directly in your HTML file:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.30.1/moment.min.js"></script>
```

## Basic Usage

To start using Moment.js, you need to import it into your JavaScript file:

```javascript
import moment from 'moment';
```

Or, if you're using it in a browser without a module bundler:

```javascript
const moment = window.moment;
```

## Creating Moment Objects

You can create a Moment object in several ways:

```javascript
// Current date and time
const now = moment();

// From a string
const dateString = moment("2023-04-15");

// From a Date object
const dateObject = moment(new Date());

// Specific date and time
const specificDate = moment("2023-04-15 14:30:00");
```

## Parsing Dates

Moment.js can parse various date formats:

```javascript
moment("2023-04-15");
moment("15/04/2023", "DD/MM/YYYY");
moment("April 15, 2023", "MMMM D, YYYY");
```

## Formatting Dates

You can format dates using various tokens:

```javascript
const date = moment("2023-04-15");
console.log(date.format("YYYY-MM-DD")); // "2023-04-15"
console.log(date.format("dddd, MMMM Do YYYY")); // "Saturday, April 15th 2023"
console.log(date.format("HH:mm:ss")); // "00:00:00"
```

## Manipulating Dates

Moment.js provides methods to manipulate dates:

```javascript
const date = moment("2023-04-15");

// Add time
console.log(date.add(1, 'day').format("YYYY-MM-DD")); // "2023-04-16"
console.log(date.add(1, 'month').format("YYYY-MM-DD")); // "2023-05-16"

// Subtract time
console.log(date.subtract(1, 'year').format("YYYY-MM-DD")); // "2022-05-16"

// Start of time unit
console.log(date.startOf('month').format("YYYY-MM-DD")); // "2022-05-01"

// End of time unit
console.log(date.endOf('year').format("YYYY-MM-DD")); // "2022-12-31"
```

## Querying Dates

You can compare and query dates:

```javascript
const date1 = moment("2023-04-15");
const date2 = moment("2023-04-20");

console.log(date1.isBefore(date2)); // true
console.log(date1.isAfter(date2)); // false
console.log(date1.isSame(date2)); // false

console.log(date1.isSame(date2, 'month')); // true
console.log(date1.isSame(date2, 'day')); // false
```

## Duration

You can work with durations:

```javascript
const duration = moment.duration(2, 'hours');
console.log(duration.asMinutes()); // 120

const date = moment("2023-04-15");
console.log(date.add(duration).format("YYYY-MM-DD HH:mm")); // "2023-04-15 02:00"
```

## Locale Support

Moment.js supports localization:

```javascript
moment.locale('fr');
console.log(moment("2023-04-15").format('LL')); // "15 avril 2023"

moment.locale('es');
console.log(moment("2023-04-15").format('LL')); // "15 de abril de 2023"
```

## Important Note

As of 2023, Moment.js is considered a legacy project and is in maintenance mode. For new projects, consider using more modern alternatives like date-fns or Luxon. However, Moment.js remains widely used and supported in many existing projects.

For more detailed information and advanced usage, please refer to the [full documentation](https://momentjs.com/docs/).