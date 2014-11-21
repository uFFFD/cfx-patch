# Patches for cfx

`cfx` is a python cli tool for developing Firefox add-ons.
It's a part of Mozilla's [Addon SDK](https://github.com/mozilla/addon-sdk/).
Current latest version is **1.17**, it's probably the last version using `cfx`.
Older versions can be found on [release page](https://github.com/mozilla/addon-sdk/releases) or [mozilla ftp](http://ftp.mozilla.org/pub/mozilla.org/labs/jetpack/).

## License

[MPL 2.0](https://www.mozilla.org/MPL/2.0/)

## How to use

### check

`git apply --check patch`

### apply

`git apply patch`

### remove

`git apply --reverse patch`

## Patches

### [Bug906359](https://bugzilla.mozilla.org/show_bug.cgi?id=906359)

Rename "fullName" key to "title" in package.json

Author: [zombie](https://github.com/zombie)

- **Bug906359-rename-fullname-to-title.patch** applies to **1.14**

### [Bug958609](https://bugzilla.mozilla.org/show_bug.cgi?id=958609)

Add-on SDK 1.15 incompatible with Python 2.7.6

- **Bug958609-python276-compatible.patch** applies to **1.14** and **1.15**

### [Bug661083](https://bugzilla.mozilla.org/show_bug.cgi?id=661083)

Let developers localize add-on metadata

Author: [TGOS](https://github.com/TGOS), [erikvold](https://github.com/erikvold)

use "extensions.\<EXTENSION_ID\>.title", "extensions.\<EXTENSION_ID\>.author", "extensions.\<EXTENSION_ID\>.description" and "extensions.\<EXTENSION_ID\>.homepage" in properties files to localize addon metadata

- **Bug661083-metadata-l10n.patch** applies to **1.14**~**1.17**

1.14 note: need to apply "Bug906359-rename-fullname-to-title.patch" **before** apply this one

### [Bug777856](https://bugzilla.mozilla.org/show_bug.cgi?id=777856)

CFX arguments for passing in prefs

add "--user-prefs" option to `cfx run`, `cfx test`, e.g.: `cfx run --user-prefs user.json`, `cfx test --user-prefs user1.json,user2.json`

- **Bug777856-prefs.patch** applies to **1.15**~**1.17**
- **Bug777856-prefs-1.14.patch** applies to **1.14**

### [Bug1036270](https://bugzilla.mozilla.org/show_bug.cgi?id=1036270)

cfx ignores command line options if they are already defined in local.json

allow user using `cfx run -g CONFIG -b path/to/binary` to override options of `CONFIG` from local.json with command line options

- **Bug1036270-cli-options-over-config.patch** applies to **1.15**~**1.17**
- **Bug1036270-cli-options-over-config-1.14.patch** applies to **1.14**

### Misc

- use "wb" instead of "w" for some files' open mode when `cfx xpi`
  - **use-wb-mode-when-xpi.patch** applies to **1.15**~**1.17**
  - **use-wb-mode-when-xpi-1.14.patch** applies to **1.14**
