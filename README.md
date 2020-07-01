Android Auto for IDrive
=======================

[![Build Status](https://travis-ci.org/hufman/AndroidAutoIdrive.svg?branch=master)](https://travis-ci.org/hufman/AndroidAutoIdrive)
[![Coverage Status](https://coveralls.io/repos/github/hufman/AndroidAutoIdrive/badge.svg?branch=master)](https://coveralls.io/github/hufman/AndroidAutoIdrive?branch=master)
[![Release Download](https://img.shields.io/github/release/hufman/AndroidAutoIdrive.svg)](https://github.com/hufman/AndroidAutoIdrive/releases/latest)
[![Gitter](https://badges.gitter.im/AndroidAutoIdrive/community.svg)](https://gitter.im/AndroidAutoIdrive/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
[<img title="Buy me a coffee" src="https://cdn.buymeacoffee.com/buttons/default-blue.png" width="85" height="20" />](https://www.buymeacoffee.com/q4JVoxz)

The BMW/Mini IDrive does not offer native Android Auto integration, but does provide a much more powerful Connected Apps connectivity option, which offers many exciting integration points into the car. This project is an effort to implement most of the features of Android Auto as unofficial BMW/Mini Connected Apps.

By relying on the Connected Apps technology, this app is automatically themed to fit natively in the car and easily connects to the car without needing any modifications. Any MY2014 or newer BMW or Mini equipped with the "Navigation System Professional (S609A)" [option](https://www.mdecoder.com/) should be compatible.

[![App List](https://hufman.github.io/AndroidAutoIdrive/demo-applist.gif)<br />Gallery](https://hufman.github.io/AndroidAutoIdrive/gallery.html)

Overview
--------

As part of the Connected Apps feature, when the phone connects over USB (or Bluetooth in 2017+ models), a tunnel to the car is created to allow other apps on the phone to interact with the car.
A Connected App uses this connection to upload its widget layout to the car, receive event callbacks from user selections, and update widget contents in response.
This remote UI framework effectively creates a custom application in the car, while enabling tight user integration and excellent data availability due to actually running all logic on the phone.

Android Auto for IDrive, combined with the safety benefits of the tactile IDrive controller, allows the user to safely interact with their incoming notifications and control their phone's music, while the phone is tucked out of reach.

Getting Started
---------------

This app requires the Connected Classic app installed to authenticate to the car. For example, if you have the BMW Connected app for your BMW, you should install the Mini Connected Classic app.

Download the APK from the [Releases page](https://github.com/hufman/AndroidAutoIdrive/releases/latest). Choose the one that says "sentry" to automatically upload crash reports, or choose "nonalytics" otherwise. After starting, the app should detect the Connected Classic app and start waiting for the car connection.

Check out the [FAQ](https://hufman.github.io/AndroidAutoIdrive/faq.html) if you run into problems.

User Guide
----------

![Phone Connection](https://hufman.github.io/AndroidAutoIdrive/screenshot-connection.png)

After connecting the phone to the car, the official Connected app should show this car icon in the status bar. When this icon appears, this app should connect and add its functionality to the car.

See [this guide](https://hufman.github.io/AndroidAutoIdrive/connection.html) for tips on improving the connection reliability of the Connected app.

![Phone App List](https://hufman.github.io/AndroidAutoIdrive/screenshot-phoneapps.jpg)

After all the apps are connected, a bunch of new entries will show up in the car's Connected menu. Besides the official Calendar and Connected apps (and the Spotify app if running over Bluetooth), there should be a new Audioplayer icon and a book icon with no label. This book icon is the Notifications app.

![Music App List](https://hufman.github.io/AndroidAutoIdrive/screenshot-medialist.jpg)

Several new entries will be added to the Media section of the control screen. The Audioplayer icon is the one with the main functionality, while the other displayed apps above the Audioplayer are quick shortcuts to switch playback to the respective apps. This screenshot also shows the official Spotify app at the bottom of the list.

Implemented Features
--------------------

  - Phone Notifications
    - Popup about new notifications
    - Supports Dismiss, Mark As Read, or other notification actions
  - Google Maps
    - Basic search and routing
    - Includes some dark themes
    - Not compiled by default, because showing Google Maps in a car is against the Maps API license
  - Control of Android Auto compatible music apps
    - Supports browsing and searching apps' music libraries
    - Supports selecting from a list of currently-queued songs, as well as basic back/next control
    - Integrates into the car's audio context, for automatic resume and hardware button control
    - Supports controlling any active music session, even apps that aren't Android Auto compatible
    - Instantly updates the screen to follow the active app
    - Tested working apps:
      - Audiobooks and Podcasts:
        - [AntennaPod](https://play.google.com/store/apps/details?id=de.danoeh.antennapod)
        - [The Bob & Tom Show](https://play.google.com/store/apps/details?id=com.radio.station.BOB.TOM)
        - [Castbox](https://play.google.com/store/apps/details?id=fm.castbox.audiobook.radio.podcast)
        - [iVooz](https://play.google.com/store/apps/details?id=com.ivoox.app)
        - [Player FM](https://play.google.com/store/apps/details?id=fm.player)
        - [Voice Audiobook Player](https://play.google.com/store/apps/details?id=de.ph1b.audiobook)
      - Music Library
        - [Black Player](https://play.google.com/store/apps/details?id=com.musicplayer.blackplayerfree)
        - [DSub](https://play.google.com/store/apps/details?id=github.daneren2005.dsub)
        - [jetAudio HD](https://play.google.com/store/apps/details?id=com.jetappfactory.jetaudio)
        - [Media Monkey](https://play.google.com/store/apps/details?id=com.ventismedia.android.mediamonkey)
        - [Plex](https://play.google.com/store/apps/details?id=com.plexapp.android) (only music and podcasts)
        - [PowerAmp](https://play.google.com/store/apps/details?id=com.maxmpz.audioplayer)
        - [Retro Music Player](https://play.google.com/store/apps/details?id=code.name.monkey.retromusic)
        - [Rocket Player](https://play.google.com/store/apps/details?id=com.jrtstudio.AnotherMusicPlayer)
        - [VLC For Android](https://play.google.com/store/apps/details?id=org.videolan.vlc)
      - Radio
        - [AP News](https://play.google.com/store/apps/details?id=mnn.Android)
        - [Dash Radio](https://play.google.com/store/apps/details?id=com.dashradio.dash)
        - [Energy Radio](https://play.google.com/store/apps/details?id=radioenergy.app)
        - [Nederland.FM](https://play.google.com/store/apps/details?id=nl.nibbixsoft.app)
        - [NHL](https://play.google.com/store/apps/details?id=com.nhl.gc1112.free)
        - [ntv Nachrichten](https://play.google.com/store/apps/details?id=de.lineas.lit.ntv.android)
        - [NYTimes](https://play.google.com/store/apps/details?id=com.nytimes.android)
        - [Radio FM](https://play.google.com/store/apps/details?id=com.radio.fmradio)
        - [Scanner Radio](https://play.google.com/store/apps/details?id=com.scannerradio)
        - [SiriusXM](https://play.google.com/store/apps/details?id=com.sirius)
        - [Versuz Radio](https://play.google.com/store/apps/details?id=com.versuzradio)
        - [Virgin Radio Italy](https://play.google.com/store/apps/details?id=it.froggy.android.virginradio)
      - Streaming Services
        - [Apple Music](https://play.google.com/store/apps/details?id=com.apple.android.music)
        - [SoundCloud](https://play.google.com/store/apps/details?id=com.soundcloud.android)
        - [Spotify](https://play.google.com/store/apps/details?id=com.spotify.music)
        - [Tidal](https://play.google.com/store/apps/details?id=com.aspiro.tidal)

Integration Points
------------------

Besides showing a self-contained remote UI, the IDrive system offers many exciting integration points. Here are a few that this project supports:

  - The UI widgets automatically take on the respective theme to fit the car
  - The Map View, Notification List, and Music Playback screens can be assigned to the physical shortcut keys in the dashboard
  - New notifications trigger a popup from anywhere in IDrive, not just in the main list
  - New notification popups can be disabled if a passenger is detected in the seat
  - The currently-playing app is displayed along the top of the IDrive screen
  - The currently-playing song is shown in the Multimedia side panel of the IDrive
  - With an old-enough phone or a new-enough car, audio focus can be enabled which grants the following extra features:
    - The Media shortcut button opens this app when it is in control of the music
    - Automatically resumes playback when reconnecting to the car
    - Playback pauses when pushing the mute button or during calls
    - The physical back/next buttons can be held down to seek within a track or pressed to skip tracks
    - The steering wheel controls can skip tracks from the instrument cluster
    - Enqueued songs can be scrolled in the instrument cluster, depending on app support

Limitations
-----------

This project replicates some of the features of Android Auto using the IDrive interface, using the same APIs that Android Auto uses to talk to the music apps. It cannot currently provide more advanced Android Auto features, such as:

  - Integration with the car's Voice Assistant button
  - Screen-casting of arbitrary phone apps to the car (Google Maps, Waze, or any other apps)
  - Displaying the original Android Auto interface at all

Due to the unofficial reverse-engineered nature of this project, it has some limitations:

  - The main menu entries' icons and text can't be altered, and so do not look exactly correct
  - The individual music source icons may not be fully functional, but they do switch the active music source
  - Android Oreo disabled Android Open Accessory Protocol 2 audio output, which is required to play audio over the app's USB connection in model years 2014-2017. Please disable the app option "Request Audio Focus" and use Bluetooth audio
  - Some Android Auto music apps enforce a whitelist of clients, preventing this app from launching them or browsing their libraries. However, once they are running, they can be controlled. For example, these popular music apps can not be launched, they must be started manually:
    - Amazon Music
    - Audible
    - Bandcamp
    - CloudPlayer
    - Deezer
    - doubleTwist
    - Google Play Music
    - iHeartAuto
    - TuneIn Radio
    - Pandora
    - Scribd
    - Smart Audiobook Player
    - YouTube Music
  - Recent versions of Spotify block the standard Android MediaBrowserService connection, which is needed for the Search feature. Please downgrade to [version 8.4.96.953](https://www.apkhere.com/down/com.spotify.music_8.4.96.953_free) for full functionality.

Requirements
------------

To communicate to the car, this project relies on the proxy connection that is created by the main Connected app on the phone. Both of the brand-specific Connected and the Connected Classic apps have been tested as compatible for this purpose.

Additionally, the car proposes a security challenge during the connection process, and this project asks the Security Service provided by the Connected apps for the correct response.
The Connected Classic app can be installed to easily provide this response. However, the newer Connected app disabled this ability in version 5.1, which means a workaround needs to be found if the user wants the features of the newer app.
For example, the user can install BMW Connected for the cloud connectivity and better robustness with the Android memory manager, and install Mini Connected Classic to provide the Security Service for this project.

It is not recommended to install both the Connected and Connected Classic apps of the same brand, they will fight over the connection to the car and undefined results may happen. Instead, install the Connected Classic app of the other brand that is not intended to be used regularly.

Build Instructions
------------------

  - (Optional) Add a [Google Maps API key](https://developers.google.com/maps/documentation/android-sdk/signup) to `~/.gradle/gradle.properties` as a property named `AndroidAutoIdrive_GmapsApiKey`. This key should have access to Maps SDK for Android, Places API, and Directions API.
  - (Optional) Add a [Spotify API Client ID](https://developer.spotify.com/dashboard/) to `~/.gradle/gradle.properties` as a property named `AndroidAutoIdrive_SpotifyApiKey`. It needs a Redirect URI set to `me.hufman.androidautoidrive://spotify_callback`, but no other settings are needed.
  - Check out the project in Android Studio, then `Build > Make Project`
  - Commandline builds should work too:
    - Make sure Android SDK Build Tools version 28 is installed
    - `git clone https://github.com/hufman/AndroidAutoIdrive.git && cd AndroidAutoIdrive`
    - `git submodule init && git submodule update`
    - `./gradlew assembleNomapNonalyticsDebug`  This step will fail without the Build Tools installed

The built APKs should be found in `app/build/outputs/apk/*/*/*.apk`

Besides building the entire project, Android Studio also offers a convenient "Run app" method to build and directly install to a connected phone. Use the Build Variants panel to select a specific version to install.

Privacy
-------

This project contains no advertising or user tracking, and is developed entirely for fun and to enhance the usefulness of the BMW/Mini infotainment system.

The app uses the Internet Permission to make a TCP connection to the car, which is reachable through a localhost socket on the main Connected app. Additionally, some cover art and incoming picture notifications (such as from Hangouts) may be fetched from Internet URLs. No other Internet access is required for the app's functionality.

The analytics-enabled version automatically reports some information to [Sentry](https://www.sentry.io) to assist with development and debugging. Besides any unfortunate crashes, the app reports any [installed music apps](https://github.com/hufman/AndroidAutoIdrive/blob/master/app/src/sentry/java/me/hufman/androidautoidrive/Analytics.kt) and the capabilities each app provides, as well as the [model and capabilities](https://github.com/hufman/AndroidAutoIdrive/blob/master/app/src/main/java/me/hufman/androidautoidrive/CarInformationDiscovery.kt#L33) of any connected car.

Each release provides both the analytics-enabled and analytics-disabled options.

<details>
  <summary>Example Analytics Data</summary>

  ### Music App
```
{
  "appId": "github.daneren2005.dsub",
  "appName": "DSub",
  "controllable": "false",
  "connectable": "true",
  "browseable": "true",
  "searchable": "false",
  "playsearchable": "false"
}
```

  ### Car Connection
```
{
  "a4axl": "true",
  "alignment_right": "true",
  "hmi_display_height": "480",
  "hmi_display_width": "1280",
  "hmi_role": "HU",
  "hmi_type": "MINI ID5",
  "hmi_version": "EntryEvo_ID5_1903_Release ID5_1903-490-1837K Build 47 - Rev:203015 2018-11-14 08:39:42",
  "inbox": "true",
  "map": "true",
  "navi": "true",
  "pia": "true",
  "speech2text": "true",
  "speedlock": "true",
  "touch_command": "false",
  "tts": "true",
  "vehicle_country": "US",
  "vehicle_productiondate": "03.00",
  "vehicle_type": "F56",
  "voice": "false"
}
```

