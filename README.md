# Jalali UI Dates for exteraGram/AyuGram
**Author:** [@MSadraShakouri](https://github.com/MSadraShakouri) | **Version:** 1.0.5

This plugin globally replaces Gregorian dates displayed in the app's UI with Jalali (Shamsi/Persian) dates. It intercepts Telegram's native `LocaleController` to dynamically convert and inject Jalali dates and standardized relative times across almost all text surfaces in the app.

## Features
- **Universal Date Hooking:** Enforces Jalali dates in the Chat List (Main Menu), In-Chat Timestamps, Media Overviews, Voice Notes, Last Seen/Online status, Call Logs, Group/Channel Joins, Scheduled Messages, and Ban dialogs.
- **Vague Last Seen Overrides:** If a user hides their last seen, the vague relative statuses ("last seen recently", "last seen within a week", "last seen a long time ago") are universally unified to English or Persian, completely overriding the app's internal locale constraints.
- **Strict Language Adaptation:** It seamlessly respects your active Telegram App language and standardizes the entire experience:
  - **Persian (`fa`)**: Displays Persian months (فروردین), Persian days (شنبه), native relative texts (امروز/دیروز), Persian vague statuses (آخرین بازدید اخیراً), and uses Eastern Arabic numerals (`۰-۹`).
  - **Other Languages (English Fallback)**: Translates to English text ("Farvardin", "Saturday", "Today", "Yesterday", "last seen within a week") and utilizes standard ASCII digits (`0-9`). This guarantees that if a user has their app set to Russian or Chinese, they still get a clean, English-based Jalali calendar system.
- **Dependency-Free:** Calculates Jalali leap years internally using a lightweight port of standard astronomical converters. No need to install external `pip` modules.
- **One-Click Installation:** Written in exteraGram's native `.plugin` format for instant deployment.

## Installation
1. Download the `jalali_ui_dates.plugin` file.
2. Send the file to your **Saved Messages** within the exteraGram or AyuGram app.
3. Tap on the file within the chat. A prompt will appear.
4. Tap **INSTALL PLUGIN**.
5. Navigate to **Settings > exteraGram/AyuGram Preferences > Plugins**, and ensure `Jalali UI Dates` is enabled.
6. **Force close and restart** the app to purge Telegram's cached strings.

## How It Works
The plugin utilizes the built-in Chaquopy Xposed-style hook engine to intercept the core Java `LocaleController` methods natively. By intercepting these requests globally (including `formatUserStatus`), it overrides the layout texts and translates them uniformly before reaching the UI rendering threads.

_Note: This plugin applies everywhere text dates are shown. Structural UI replacements (like replacing the interactive Date Picker Calendar View) are not covered by these simple string hooks and require native Android UI injections._