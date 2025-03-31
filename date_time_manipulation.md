# Date and Time Manipulation with Moment.js

Moment.js provides powerful tools for working with dates and times in JavaScript. This guide covers essential techniques for manipulating dates and times, including adding and subtracting time, comparing dates, and working with durations.

## Table of Contents

1. [Creating Moment Objects](#creating-moment-objects)
2. [Adding and Subtracting Time](#adding-and-subtracting-time)
3. [Comparing Dates](#comparing-dates)
4. [Working with Durations](#working-with-durations)
5. [Parsing and Formatting](#parsing-and-formatting)

## Creating Moment Objects

Before manipulating dates and times, you need to create Moment objects. Moment.js offers several ways to do this:

```javascript
// Current date and time
const now = moment();

// Specific date and time
const specificDate = moment('2023-05-15T12:30:00');

// Unix timestamp (in milliseconds)
const unixDate = moment.unix(1621077000);

// UTC date
const utcDate = moment.utc('2023-05-15T12:30:00Z');
```

## Adding and Subtracting Time

Moment.js makes it easy to add or subtract time from a date:

```javascript
const date = moment('2023-05-15T12:30:00');

// Adding time
date.add(1, 'day');
date.add(2, 'hours');
date.add(30, 'minutes');

// Subtracting time
date.subtract(1, 'week');
date.subtract(3, 'months');
date.subtract(5, 'years');
```

You can chain these methods for multiple operations:

```javascript
const newDate = date.add(1, 'day').subtract(2, 'hours').add(30, 'minutes');
```

## Comparing Dates

Moment.js provides several methods for comparing dates:

```javascript
const date1 = moment('2023-05-15');
const date2 = moment('2023-06-01');

// Check if a date is before another
console.log(date1.isBefore(date2)); // true

// Check if a date is after another
console.log(date2.isAfter(date1)); // true

// Check if dates are the same
console.log(date1.isSame(date2)); // false

// Find the difference between dates
const diff = date2.diff(date1, 'days');
console.log(diff); // 17
```

## Working with Durations

Moment.js allows you to create and manipulate durations:

```javascript
// Create a duration
const duration = moment.duration({
    days: 2,
    hours: 8,
    minutes: 30
});

// Add duration to a date
const date = moment('2023-05-15');
const newDate = date.add(duration);

// Subtract duration from a date
const earlierDate = date.subtract(duration);

// Get humanized output of a duration
console.log(duration.humanize()); // "2 days"
```

You can also set relative time thresholds and rounding:

```javascript
// Set relative time threshold
moment.relativeTimeThreshold('s', 60);
moment.relativeTimeThreshold('m', 60);
moment.relativeTimeThreshold('h', 24);

// Set relative time rounding
moment.relativeTimeRounding(Math.floor);
```

## Parsing and Formatting

Moment.js excels at parsing and formatting dates:

```javascript
// Parse a string date
const parsedDate = moment('2023-05-15', 'YYYY-MM-DD');

// Format a date
console.log(parsedDate.format('MMMM Do, YYYY')); // May 15th, 2023

// ISO 8601 formatting
console.log(parsedDate.toISOString());
```

By mastering these date and time manipulation techniques, you'll be able to handle complex date-related operations in your JavaScript applications with ease using Moment.js.