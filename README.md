# Userscripts Safari

An open-source userscript editor for Safari.

![Userscripts Safari](/etc/screenshot.png)

## Installation

Install via [Mac App Store](https://itunes.apple.com/us/app/userscripts/id1463298887) or clone the project and build with Xcode.

**If you are looking for the old/simplified version of this extension, please check out [InjectJS](https://github.com/quoid/InjectJS).**

## Usage

**Version 2 and above requires Safari 13+**

As of Version 2.0.0, this extension now supports multiple, domain specific, userscripts as well as supporting 2 different "userscript" types. It supports traditional javascript userscripts as well and css "userscripts" (or more commonly referred to as, userstyles).

Click the extension's toolbar button to open the extension UI.

If you don't feel like reading, visit [this folder](/etc/videos/) to watch some short and poorly made video tutorials.

**UI Overview**
![Userscripts Safari](/etc/ui-overview-01.png)
![Userscripts Safari](/etc/ui-overview-02.png)

1. **Create New Userscript Button** - Click this button to create a new userscript. You will be able to choose what type of userscript you would like to create (css or js)
1. **Userscript Filter** - You can use this to filter through your existing userscript. **Note**, this element filters by userscript title, not desription. It supports the following flags to help you filter more efficiently: `!js`, `!css`, `!disabled`, `!enabled`
1. **Userscript Toggle** - Toggling this element with enable/disable it's injection into webpages
1. **Editor** - The editor; the place where you write the code for the userscripts
1. **Download Button** - Click this to download a copy of your userscript
1. **Delete Button** - Click this to delete the userscript; *note:* deleted userscripts get put into your trash bin
1. **Settings Button** - Click this to open the settings modal
1. **Status Info** - Look here for status message pertaining to the currently opened userscript
1. **Discard/Save Buttons** - After editing a userscript, clicking on the "discard" button will remove any changes made since the userscript was loaded; clicking on the "save" button will save your changes to the userscript
1. **Sidebar** - Newly added/created scripts go here
1. **Settings Modal** - The various settings for the extension
1. **Global Blacklist** - Domain patterns entered here will be excluded from userscript injection; adding `*://*.*` to the global blacklist will turn off injection for all userscripts

## Userscript Metadata

Version 2.0.0 introduces the common practice of using userscript metadata to drive certain functionality. The currently supported fields will be listed below. There *are* plans to support more fields in future updates.

- `@name` - This will be the name that displays in the sidebar and be used as the filename - you can not use the same name for multiple scripts of the same type
- `@description`- Use this to describe what your userscript does - this will be displayed in the sidebar - there is a setting to hide userscript descriptions
- `@match` - Domain match patterns - you can use several instances of this field if you'd like multiple domain matches - view [this article for more information on constructing patterns](https://developer.chrome.com/extensions/match_patterns)
- `@exclude-match` - Domain patterns where you do *not* want the script to run
- `@include` - An alias for `@match` - functions exactly like `@match`
- `@exclude` - An alias for `@exclude-match` - functions exactly like `@exclude-match`

**All userscripts need at least 1 `@match` or `@include` to run!**

CSS Userscripts/styles can use the javascript metadata format or the Userstyle format. Both formats shown below are valid for **css** type.

```js
// ==UserScript==
// @name           Example
// @description    An example
// @match          *://github.com/*
// @match          *://*.github.com/*
// ==/UserScript==
```

```css
/* ==UserStyle==
@name           Example
@description    An example
@match          *://github.com/*
@match          *://*.github.com/*
==/UserStyle== */
```
## Notes & FAQs

**Do I need to use the extension's editor to create new userscripts or to edit existing?**

No; simply put your userscript in the extension's scripts folder. You can easily access this folder by clicking the link in the extension's settings modal option labelled "Save Location" or by visiting `~/Library/Containers/com.userscripts.macos.Userscripts-Extension/Data/Documents/scripts/`.

If you are adding a new userscript, before injection will occur, you must open the extension UI by clicking on the extension's toolbar button. If you are editing an existing userscript through your own editor, you should not need to open the ui for the changes to take effect.

**Can I change the location where my files are saved?**

Not yet, but this is planned in a future update.

**Are there any keyboard shortcuts?**

Currently there is only one keyboard shortcut - `cmd+s` to save changes. *Note:* normal shortcuts like `cmd+z`, `cmd+shift+z`, etc... like you would have on any other normal webpage should still function.

**I updated from Version 1.5.0, where did my previous userscript go?**

Your previous userscript file *should* still exist after update. You can access its folder by clicking the link in the extension's settings modal option labelled "Save Location" or by visiting `~/Library/Containers/com.userscripts.macos.Userscripts-Extension/Data/Documents/`.

## Feedback & Support
If you need help doing something with this extension or you have an idea for an enhancement, please open an issue. Be sure to search current and closed issues before opening a new one.

## Donate

## Privacy Policy
Userscripts does not collect any data from its users nor monitor activities or actions you perform within the application and extension. This means everything that you do with the application and extension is private to you and is never shared with the developers or third parties. Since there is no data collection, there is no data retention of any kind.

## License

Licensed under the [GNU General Public License v3.0](/LICENSE) license for all open source applications. A commercial license is required for all commercial applications.



