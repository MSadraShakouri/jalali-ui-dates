# Jalali UI Dates for exteraGram/AyuGram
**Author:** [@MSadraShakouri](https://github.com/MSadraShakouri) | **Version:** 1.0.8

This plugin converts Gregorian dates shown in Telegram's UI to Jalali (Shamsi/Persian) dates. It hooks Telegram's native `LocaleController` to format dates and timestamps across the chat list, message timestamps, media overviews, voice notes, last-seen timestamps, call logs, group/channel joins, scheduled messages, and ban dialogs.

## Features
- **Relative date labels are retained:** The plugin continues to use “Today”, “Yesterday”, and weekday labels where appropriate, alongside exact Jalali dates.
- **Native vague last-seen wording:** Statuses such as “last seen recently” and “within a week/month” are left to Telegram's own localized `formatUserStatus`; the plugin no longer replaces them with forced English or Persian text.
- **Language support:**
  - **Persian (`fa`)**: Persian month names, relative labels, and Eastern Arabic numerals (`۰-۹`).
  - **Chinese (`zh`)**: Chinese date order and translations for relative labels and other plugin-generated words (for example, `1405年1月2日`), with Traditional Chinese wording for Traditional locales such as Taiwan, Hong Kong, and Macau.
  - **Other languages**: English month names and plugin-generated labels, with standard ASCII digits (`0-9`). Telegram-native vague status text remains in the app's selected language.
- **Dependency-free:** Calculates Jalali dates internally without external Python modules.
- **One-click installation:** Packaged as exteraGram's native `.plugin` file.

## Installation
1. Download `jalali_ui_dates.plugin`.
2. Send the file to your **Saved Messages** in exteraGram or AyuGram.
3. Tap the file and choose **INSTALL PLUGIN**.
4. Go to **Settings > exteraGram/AyuGram Preferences > Plugins** and enable **Jalali UI Dates**.
5. Force close and restart the app to refresh Telegram's cached strings.

## How It Works
The plugin hooks date-formatting methods in Telegram's `LocaleController` and converts their Gregorian timestamps to Jalali dates before they reach the UI. It does not hook `formatUserStatus`, so vague last-seen wording remains Telegram's own localized text. The interactive date picker is not changed; that requires native Android UI hooks.
