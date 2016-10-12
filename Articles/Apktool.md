# Apktool

![Apktool](/Images/Apktool/apktool0.jpg)

For all Android application hackers and reverse engineers, one of the most basic tools you would definitely have your hands-on is the `apktool`. For people who haven't heard anything about it, let's look at an introduction:

> " It is an open source tool for reverse engineering Android APK files. Not only it has the power for decompiling, it is empowered with the feature of recompiling the decompiled code "

### I'm impressed, how can I get this tool ?

You have three options:

- You could get the latest developed source code on [Github](https://github.com/iBotPeaches/Apktool) and [build](https://ibotpeaches.github.io/Apktool/build/) by yourself.
- You could download the [latest release](https://github.com/iBotPeaches/Apktool/releases) and start playing with it
- If you are an Ubuntu / Debian user : `sudo apt-get install apktool` - as simple as that

> **NOTE:** Google Chrome detects the `apktool_2.2.0.jar` as malicious and warns before completing the download whether to keep the file or discard. *If you wish to discard, there's no use of reading the rest of the article*.

You could read about the latest release v2.2.0 (at the time of writing) [here](http://connortumbleson.com/2016/08/07/apktool-v2-2-0-released/).

To see how accurate the code decompilation works lets use [a google sample android project](https://github.com/googlesamples/android-ActionBarCompat-Styled) as example. Let's compile it and then decompile to compare the original source code with the decompiled source code.

For this example, [Android Tamer](https://androidtamer.com/) is used. Android Tamer is an open-source virtual platform (VM image) for both offensive security testing and development of Android applications. It comes with `apktool` and many more awesome tools pre-installed.

### Compiling the sample Android app

Using [Android Studio](https://developer.android.com/studio/index.html), the sample android app's source code was compiled and built into a signed apk file. The compiled Android app is saved as `Application-release.apk`. Here's a screenshot of its AndroidManifest.xml file:

![AndroidManifest original code](/Images/Apktool/apktool1.jpg)

### Decompiling the Android app

Decompiling the Android app is easy using apktool. The required command is:

`apktool d <apkfilename>.apk`

where `d` denotes decompile the apk file.

![Apktool commandline usage](/Images/Apktool/apktool2.jpg)

Using the above command creates a folder with the name same as that of the apk file (in this case the folder's name is Application-release).

![Folder](/Images/Apktool/apktool3.jpg)

When you enter inside the folder, you could see many folders and a file : `AndroidManifest.xml`

![Output of apktool](/Images/Apktool/apktool4.jpg)

Lets have a look at the manifest file:

![Decompiled AndroidManifest file](/Images/Apktool/apktool5.jpg)

On comparing both the original and the decompiled source code, you could see that the comments are stripped off and there are some slight changes with the indentation. As a result you can't say that the entire reverse-engineered source code is exact as the original, but it works when you compile it again.

There is a very good and advanced [official documentation](https://ibotpeaches.github.io/Apktool/documentation/), you could read more about the version changes and bug fixes there.

If you are a developer and want to contribute to this project, check out the [project's contribution instructions](https://ibotpeaches.github.io/Apktool/contribute/) and start enhancing the power of open source tools.
