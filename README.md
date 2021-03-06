[![Build Status](https://travis-ci.org/gnunn1/tilix.svg?branch=master)](https://travis-ci.org/gnunn1/tilix)
# Tilix
A tiling terminal emulator for Linux using GTK+ 3. The Tilix web site for users is available at [https://gnunn1.github.io/tilix-web](https://gnunn1.github.io/tilix-web).

*Note that Terminix is changing it's name to Tilix due to a trademark issue with the Terminix International Corporation. It may take a few weeks to complete the process, thank you in advance for your patience while we work through this change.*

###### Screenshot
![Screenshot](http://www.gexperts.com/img/terminix/terminix11.png)

### About

Tilix is a tiling terminal emulator which uses the VTE GTK+ 3 widget with the following features:

* Layout terminals in any fashion by splitting them horizontally or vertically
* Terminals can be re-arranged using drag and drop both within and between windows
* Terminals can be detached into a new window via drag and drop
* Input can be synchronized between terminals so commands typed in one terminal are replicated to the others
* The grouping of terminals can be saved and loaded from disk
* Terminals support custom titles
* Color schemes are stored in files and custom color schemes can be created by simply creating a new file
* Transparent background
* Background images
* [Quake mode](https://github.com/gnunn1/tilix/wiki/Quake-Mode) support (i.e. drop-down terminal)
* Custom hyperlinks
* Automatic (triggered) profile switches based on hostname and directory
* Supports notifications when processes are completed out of view. Requires the Fedora notification patches for VTE
* Experimental trigger support (Requires patched VTE, see [wiki ](https://github.com/gnunn1/tilix/wiki/Automatic-(Triggered)-Profile-Switching))
* Experimental badge support (Requires patched VTE, see [wiki](https://github.com/gnunn1/tilix/wiki/Badges)

The application was written using GTK 3 and an effort was made to conform to GNOME Human Interface Guidelines (HIG). As a result, it does use CSD (i.e. the GTK HeaderBar) though it can be disabled if necessary. Other than GNOME, only Unity has been tested officially though users have had success with other desktop environments.

### Dependencies

Tilix requires the following libraries to be installed in order to run:
* GTK 3.14 or later
* GTK VTE 0.42 or later
* dconf
* GSettings
* [Nautilus-Python](https://wiki.gnome.org/Projects/NautilusPython) (Required for Nautilus integration)

### Support

If you are having issues with Tilix, feel free to open issues here in github as necessary. Developers and users can  also be found on IRC on the [freenode](https://freenode.net) network in the #tilix room.

### Localization

Tilix is localized using Weblate, please visit the Weblate hosted [Tilix translations site](https://hosted.weblate.org/projects/tilix/translations) in order to assist with translations, please do not submit direct pull requests to this repository for translations.

### Building

Tilix is written in D and GTK 3 using the gtkd framework. This project uses dub to manage the build process including fetching the dependencies, thus there is no need to install dependencies manually. The only thing you need to install to build the application is the D tools (DMD and Phobos) along with dub itself. Note that D supports three compilers (DMD, GDC and LDC) and Tilix only supports DMD.

Once you have those installed, compiling the application is a one line command as follows:

```
dub build --build=release
```

The application depends on various resources to function correctly, run `sudo ./install.sh` to build and copy all of the resources to the correct locations. Note this has only been tested on Arch Linux, use with caution.

Note there is also experimental support for autotools, please see the wiki page on [autotools](https://github.com/gnunn1/tilix/wiki/Building-with-Autotools) for more information.

#### Build Dependencies

Tilix depends on the following libraries as defined in dub.json:
* [gtkd](http://gtkd.org/) >= 3.3.0
* gdk-pixbuf-pixdata (Used when building resource file)

### Install Tilix

Tilix is available as [packages](https://gnunn1.github.io/tilix-web/#packages) for a variety of distributions.

#### Uninstall Tilix

This method only applies if you installed Tilix manually using the install instructions. If you installed Tilix from a distribution package then use your package manager to remove tilix, do not use these instructions.

Download the uninstall.sh script from this repository and then open a terminal (not Tilix!) in the directory where you saved it. First set the executable flag on the script:

```
chmod +x uninstall.sh
```

and then execute it:

```
sudo sh uninstall.sh
```
