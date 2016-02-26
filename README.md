# fn.app

This is an app originally created by user **jkbrzt** in Automator. It toggles the
**"Use all F1, F2, etc. keys as standard function keys"**
option in Mac OS System Preferences. A task that is tedious
when done often (which programmers tend to do).

I recreated it using XCode so that a little icon appears in your status bar. There you can toggle the fn-keys on or off.

All it does is that it executes [this AppleScript snippet](http://apple.stackexchange.com/questions/59178/toggle-use-all-f1-f2-as-standard-keys-via-script#answer-60496):

```applescript
tell application "System Preferences"
	reveal anchor "keyboardTab" of pane "com.apple.preference.keyboard"
end tell
tell application "System Events" to tell process "System Preferences"
	click checkbox 1 of tab group 1 of window 1
end tell
quit application "System Preferences"
```


## Installation

Copy the `fn.app` folder into `/Applications`.

In OS X 10.9 (Mavericks) and later, you also need to:

1. go to `System Preferences > Security & Privacy > Accessibility > Privacy` 
2. tick `fn.app` under `Allow the apps below to control your computer`.


![preferences](https://f.cloud.github.com/assets/326885/1463976/de2c61f0-453c-11e3-9129-f0d992aeb2a8.png)


## Usage

Press the icon in your status bar.

The options ‘On’ and ‘Off’ stand for the following:
* ‘On’ means the fn-keys function as F1, F2 etc.
* ‘Off’ means the fn-keys function for the mac special features: Brightness, Volume etc.

![menu](https://github.com/Haffi921/macos-fn-toggle/blob/master/fn.screenshot.png?raw=true)