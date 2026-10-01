# Jalali UI Dates for exteraGram/AyuGram
**Author:** [@MSadraShakouri](https://github.com/MSadraShakouri) | **Version:** 1.0.7

This plugin converts Gregorian dates shown in Telegram's UI to Jalali (Shamsi/Persian) dates. It hooks Telegram's native `LocaleController` to format dates and timestamps across the chat list, message timestamps, media overviews, voice notes, last-seen timestamps, call logs, group/channel joins, scheduled messages, and ban dialogs.

## Features
- **Concrete dates, not relative labels:** Replaces “Today”, “Yesterday”, and recent weekday labels with Jalali dates. Where the chat list normally shows a clock time for a current or very recent message, it keeps that exact time. Vague last-seen states that have no exact timestamp are omitted; exact timestamps and other native status text remain visible.
- **Language support:**
  - **Persian (`fa`)**: Persian month names and Eastern Arabic numerals (`۰-۹`).
  - **Chinese (`zh`)**: Chinese date order and labels (for example, `1405年1月2日`), with Traditional Chinese wording for Traditional locales such as Taiwan, Hong Kong, and Macau.
  - **Other languages**: English month names and labels, with standard ASCII digits (`0-9`).
- **Dependency-free:** Calculates Jalali dates internally without external Python modules.
- **One-click installation:** Packaged as exteraGram's native `.plugin` file.

## Installation
1. Download `jalali_ui_dates.plugin`.
2. Send the file to your **Saved Messages** in exteraGram or AyuGram.
3. Tap the file and choose **INSTALL PLUGIN**.
4. Go to **Settings > exteraGram/AyuGram Preferences > Plugins** and enable **Jalali UI Dates**.
5. Force close and restart the app to refresh Telegram's cached strings.

## How It Works
The plugin hooks methods in Telegram's `LocaleController` and converts their Gregorian timestamps to Jalali dates before they reach the UI. It also suppresses last-seen labels when Telegram provides only a vague range rather than an exact timestamp. The interactive date picker is not changed; that requires native Android UI hooks.
