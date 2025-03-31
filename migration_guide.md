# Migration Guide

This guide is designed to help users upgrade from older versions of Moment.js to the latest version. It highlights breaking changes, deprecated features, and new functionality introduced in recent versions.

## Table of Contents

1. [Upgrading to 2.30.x](#upgrading-to-230x)
2. [Upgrading to 2.29.x](#upgrading-to-229x)
3. [Upgrading to 2.28.x](#upgrading-to-228x)
4. [Upgrading to 2.27.x](#upgrading-to-227x)
5. [Upgrading to 2.26.x](#upgrading-to-226x)
6. [Upgrading to 2.25.x](#upgrading-to-225x)
7. [Important Changes in Earlier Versions](#important-changes-in-earlier-versions)
8. [Deprecated Features](#deprecated-features)
9. [New Features and Improvements](#new-features-and-improvements)

## Upgrading to 2.30.x

### Breaking Changes

- The changes introduced in 2.30.0 related to TypeScript have been reverted in 2.30.1 due to compatibility issues. If you're using TypeScript with Moment.js, be aware of potential type-related issues when upgrading to 2.30.x.

## Upgrading to 2.29.x

### Bug Fixes

- Fixed a ReDoS (Regular Expression Denial of Service) vulnerability in the `preprocessRFC2822` regex.
- Removed usage of `const` to improve compatibility with older JavaScript environments.

## Upgrading to 2.28.x

### Bug Fixes

- Fixed a bug where `.format()` was modifying the original instance.

### Locale Updates

- Various locale improvements have been made. Check the changelog for specific updates to locales you're using.

## Upgrading to 2.27.x

### New Locales

- Added Turkmen locale.

### TypeScript Improvements

- Minor TypeScript fixes have been implemented.

## Upgrading to 2.26.x

### Packaging Changes

- ES Module bundled moment is now included in the `dist/` folder.
- This change might affect how locales are loaded and could potentially cause webpack to bundle all locales automatically unless configured otherwise.

## Upgrading to 2.25.x

### New Features

- Added support for strict string parsing.
- Improved support for eras in English and Japanese locales.
- Added ability to accept custom relative thresholds in `duration.humanize()`.

### Breaking Changes

- Changed the logic for `isValid()`.
- Week tokens parsing has been updated.

## Important Changes in Earlier Versions

### 2.24.0 and earlier

- Added short form localized tokens.
- Improved week support.
- Changed the behavior of `moment#diff` to floor instead of round.
- Removed `moment#sod` and `moment#eod` in favor of `moment#startOf` and `moment#endOf`.
- Removed `moment.humanizeDuration()` in favor of `moment.duration().humanize()`.

## Deprecated Features

- Global export of moment (will be removed in the next major version).
- `moment.lang()` is deprecated in favor of `moment.locale()`.
- `moment.min()` and `moment.max()` instance methods are deprecated in favor of `moment.min()` and `moment.max()` global methods.

## New Features and Improvements

- Added bower support.
- Improved parsing of two-digit years.
- Added `toJSON()` method for moments.
- Introduced Durations as a new feature.
- Added UTC mode support.
- Implemented automatic ISO8601 parsing.

When upgrading, always refer to the [full changelog](https://github.com/moment/moment/blob/develop/CHANGELOG.md) for a comprehensive list of changes and test your application thoroughly after updating to a new version of Moment.js.