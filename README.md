Apple Core Audio Utility Classes
================================

Introduction
------------

This is a mirror of Apple's [Core Audio Utility Classes](http://developer.apple.com/library/ios/#samplecode/CoreAudioUtilityClasses/Introduction/Intro.html) sample code.

> The "CoreAudio" folder contains the Public Utility sources (PublicUtility folder) as well as base classes required for codec and audio unit development. These utility classes are used by various Apple Core Audio sample project and extend or wrap Core Audio API's.
> 
> Recommended for anyone working with Core Audio on iOS and OS X.
> 
> The "CoreAudio" utility classes require OS X 10.7+, iOS 5.0+ and Xcode 4.3+.

Notes on CocoPods
---------------

CocoaPods is a great way to include this library, although the collection of sub-specs is a bit limited at the moment (pull requests
welcome!).

Also note that since Apple have on occasion greatly changed how some of the classes in here work, you're probably best off using the
version equality rather than `~>` so that you don't get surprised by a "minor" update in the same year.

Revision History
----------------

Every project in Apple's sample code repository has a revision history file with dates and notes.
This table is transcribed below since it's not included in the source download.

The initial checkin of this repository was made on Feburary 17 2013 which corresponds to Apple's
revision of 2013-01-02 and git tag 2013.1.2.

Git Tag    | Date                    | Notes
-----------|-------------------------|---------
2013.09.17 | `2013-09-17` | Apple notes: Fixes a build error caused by including LockFreeFIFO.h Fixes several issues with the CARingBuffer class.<br>Our notes: Apple also made the clang fixes in our `thehtb-clang-updates` branch which is now unnecessary.

2013.1.2   | `2013-01-02` | Removed the need for ACCompatibility.h included from ACBaseCodec.cpp. Removed #defines around Add/RemovePropertyListenerBlock calls in CAHALAudioObject class.
N/A        | `2012-10-31` | Fixes more analyzer warnings and updates ComponentBase.h to correctly define AUDIOCOMPONENT_ENTRY when CA_USE_AUDIO_PLUGIN_ONLY is defined.
N/A        | `2012-06-26` | Logic analyzer warnings have been fixed.
N/A        | `2012-06-13` | Core Audio Utility Classes contains Public Utility sources as well as base classes required for codec and audio unit development.

Background
----------

Apple provides a number of sets of "Public Utility Classes" designed to make a number
of standard uses of the CoreAudio C API easier. These classes used to be bundled in the
/Developer directory of pre-app store Xcode installations and many Apple sample projects
and public open source projects referenced that standard installation path. Since that
standard install is now gone, Apple provides the classes as a standalone zip download
as part of their sample code library. Consequently, Apple's sample projects (and probably
other people's projects) have started including those parts of the Public Utility Classes
as they need.

As a pseudo part of Apple's public APIs, this is a versioning and maintenance nightmare,
and also reduces discoverability as subsets of the library is scattered around.

This mirror
-----------

As I have moved to using [CocoaPods](http://cocoapods.org) for managing my projects'
dependencies I naturally wanted to manage the Core Audio Publicy Utility Classes that
way as well. The Pod is named `AppleCoreAudioUtilityClasses@thehtb` according to CocoaPod's
[non-authoritative naming policy](https://github.com/CocoaPods/CocoaPods/wiki/Contributing-to-the-master-repo).

First I considered extending the CocoaPods podspec to allow a zip file download directly
from Apple. This has a major problem that since Apple's download urls aren't versioned,
changes to the utility classes could break your project.

So instead I decided to start a GitHub mirror of the classes. The library is completely
unchanged from Apple's download (aside from the addition of this README and the LICENSE
file). This is allowed by Apple's sample code license which you can read in the LICENSE
file and in the header of each source and header file.

This mirror is maintained by Mark Aufflick of [The High Technology Bureau](http://htb.io). Please send
any questions/suggestions to [mark@htb.io](mailto:mark@htb.io).
