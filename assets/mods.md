# Notes
- According to the rules of the 4PDA resource, the public release of client app modifications is prohibited, but no one forbids using it only for yourself
- To decompile applications, use any convenient apktool for you and your device architecture

#
#

## To separate the favorites and mentions nav icons in drawer
- Add the ic_nav_men drawable resource as a bitmap or vector and edit /res/layout/mainactivity.xml in the **client app** itself

`<TextView
    android:textSize="16sp"
    android:textColor="@color/main_text"
    android:gravity="center|left"
    android:layout_width="0dp"
    android:layout_height="match_parent"
    android:text="@string/nav_new_men"
    android:includeFontPadding="false"
    android:drawableLeft="@drawable/ic_nav_men"
    android:drawablePadding="8dp"
    android:layout_weight="1.0"
    android:lineSpacingExtra="0sp" />
`

#
#

## To remove all nav icons from the drawer
- Download the [attached archive](https://github.com/PycmShoma/4PDA-DarkMaterialYou-Skin/blob/master/assets/no_nav_icons.zip) and extract the icons to the /res/drawable-xhdpi directory of the **skin app** and delete all vector resources /res/drawable/ic_nav_*.xml

#
#

## To add a monochrome app icon for A13, create a vector resource in /res/drawable on the **client app** adaptive_monochrome_fourpda_launcher.xml with content:
`<?xml version="1.0" encoding="utf-8"?>
<vector xmlns:android="http://schemas.android.com/apk/res/android"
    android:height="108dp"
    android:width="108dp"
    android:viewportWidth="108.0"
    android:viewportHeight="108.0">
    <path
        android:fillColor="#FF000000"
        android:pathData="m54 25a29 29 0 1 0 29 29 29 29 0 0 0-29-29zm13.69 45.92h-11.69l-.08-6.4h-20.45v-10l15.33-17.44h16.89z" />
    <path
        android:fillColor="#FF000000"
        android:pathData="m47.16 56.6 8.59.01v-9.56z" />
</vector>
`
and add the line to /res/mipmap-anydpi-v26/ic_launcher.xml and ic_launcher_round.xml with content:
penultimate line (before the line) </adaptive-icon>
`<monochrome android:drawable="@drawable/adaptive_monochrome_fourpda_launcher" />`
