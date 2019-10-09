# Android 10 keyboard for Android 2.3+ (Mik-el)

[![Crowdin](https://d322cqt584bo4o.cloudfront.net/simple-keyboard/localized.svg)](https://crowdin.com/project/simple-keyboard)


<img src="images/screenshot-0.png"
      alt="closeup"
      width="500"/>
- Small size
- Ads-free
- Only 1 permission (Vibrate)
# Story of this code
- Google has its stock keyboard ([official source code][googlecode])
- rkkr makes his minimal "[Simple Keyboard][simplekeyboardcode]", removing unecessary feaures from the code (Emojis, GIFs, spell checker and swipe typing) 
- Mik-el (me) works to make the keyboard working also on Android 2.3 devices (and up)  

# My steps to add support for Android 2.3+
 - Lowered minSdkVersion to api10 (android 2.3.3+);
 - Added support-v4 library to add NEW apis for this "old" android; (support library version is 25.4.0, newer ones require Android 4.0)
 - Added suport-v7 library even if (probably) unecessary
 - Added support for android.animation (requires api11+ but I've added backported code thanks to [nineoldandroid][jake]) 
 - Set the hardware acceleration for the app to "false" to avoid the usage of a newer method 

# Does this Keyboard work?
 - The code compiles correctly.
 - The generated apk is correctly installed on old Android devices
 - The keyboard crashes :(

# The last unsolved error according to logcat
 - (It's a classic "colud not find class X referenced from method Y" problem, [link][log1] but I haven't figured out how to solve it yet)
 - In other words, a java class in this code (rkr.simplekeyboard.inputmethod.latin.RichInputMethodManager) uses methods that belongs to an android class (android.view.inputmethod.InputMethodSubtype) that can't be used in this project. 

# How to quickly work on this code
Search in the whole project the word "Mikel" (Ctrl+Maiusc+F) and you'll quickly find the lines edited by me


# Credits and Support
 - Mik-el (me, works on Android 2.3+ support)
 <a href="https://paypal.me/donationMikel"><img src="https://www.paypalobjects.com/webstatic/mktg/merchant_portal/button/donate.en.png" align="center" width="160" ></a>
 - rkkr (worked on the [SimpleKeyboard][simplekeyboardcode] code)
 - Jake Wharton ([backported][jake] Android animation)
# My Social pages
|  |  |
| ------ | ------ |
| XDA Forum | [link][xda] |
| Instagram | [link][insta] |
| Youtube | [link][yt] |

[xda]: <http://bit.ly/2NBnhqB>
[insta]: <http://bit.ly/mikel_insta>
[yt]: <http://bit.ly/mikel_YT>
[googlecode]: <https://android.googlesource.com/platform/packages/inputmethods/LatinIME/>
[simplekeyboardcode]:<https://github.com/Mik-el/simple-keyboard/blob/master/README.md>
[jake]:<https://github.com/JakeWharton/NineOldAndroids/>
[log1]:<http://bit.ly/33kx8Yv>
