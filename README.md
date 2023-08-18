# Eagle Scripts

This is a collection of startup scripts to automatically configure
[Eagle][eagle-home]. These scripts configure the layer color scheme to make it
possible to distinguish layers that, by default, have identical appearances. A
set of layer visibility presets is also defined and some convenient hotkeys are
also configured.

# Description

If Eagle is set up to use these scripts, the following layers will be available
in the various editors.

| Editors                   | Available layers                                                                                                                                                                                                                                      |
| ------------------------- |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Schematic, Symbol, Device | Nets, Buses, Names, Values, Pins, Symbols, Info                                                                                                                                                                                                       |
| Board, Package            | Top, Bottom, Pads, Vias, Unrouted, Dimension, tPlace, bPlace, tOrigins, bOrigins, tNames, bNames, tValues, bValues, tStop, bStop, tCream, bCream, tKeepout, bKeepout, tRestrict, bRestrict, vRestrict, Drills, Holes, Milling, Measures, tDocu, bDocu |

The colors associated with each layer are chosen to make it possible to
distinguish them from each other. This is especially useful in distinguishing
the layers tPlace, bPlace, tNames, bNames, tValues, bValues, tDocu, and bDocu,
all of which have identical appearances in the default color scheme.

In each editor, individual layers from among the available ones can be hidden or
shown, as desired. In the board and package editors, the following layer
visibility presets are also defined, for convenience.

| Preset name       | Brief description                                                                                                         | Visible layers                                                                                                                                                                                                                         |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AIRWIRE           | Only show unrouted lines. Helps to check if routing is complete.                                                          | Unrouted, Dimension, Measures                                                                                                                                                                                                          |
| CONCISE\_TOP      | Concise top side. Shows important content of the top side without providing too much visual information.                  | Top, Pads, Vias, Unrouted, Dimension, tPlace, tOrigins, tNames, tKeepout, tRestrict, vRestrict, Milling, Measures, tDocu                                                                                                               |
| CONCISE\_BOTTOM   | Concise bottom side. Shows important content of the bottom side without providing too much visual information.            | Bottom, Pads, Vias, Unrouted, Dimension, bPlace, bOrigins, bNames, bKeepout, bRestrict, vRestrict, Milling, Measures, bDocu                                                                                                            |
| CONCISE\_ALL      | Concise top and bottom sides. Shows important content of both sides without providing too much visual information.        | Top, Bottom, Pads, Vias, Unrouted, Dimension, tPlace, bPlace, tOrigins, bOrigins, tNames, bNames, tKeepout, bKeepout, tRestrict, bRestrict, vRestrict, Milling, Measures, tDocu, bDocu                                                 |
| DETAILED\_TOP     | Detailed top side. Shows complete content of top side including layers that don't make it to the final PCB.               | Top, Pads, Vias, Unrouted, Dimension, tPlace, tOrigins, tNames, tValues, tStop, tCream, tKeepout, tRestrict, vRestrict, Milling, Measures, tDocu                                                                                       |
| DETAILED\_BOTTOM  | Detailed bottom side. Shows complete content of bottom side including layers that don't make it to the final PCB.         | Bottom, Pads, Vias, Unrouted, Dimension, bPlace, bOrigins, bNames, bValues, bStop, bCream, bKeepout, bRestrict, vRestrict, Milling, Measures, bDocu                                                                                    |
| DETAILED\_ALL     | Detailed top and bottom sides. Shows complete content of both sides including layers that don't make it to the final PCB. | Top, Bottom, Pads, Vias, Unrouted, Dimension, tPlace, bPlace, tOrigins, bOrigins, tNames, bNames, tValues, bValues, tStop, bStop, tCream, bCream, tKeepout, bKeepout, tRestrict, bRestrict, vRestrict, Milling, Measures, tDocu, bDocu |

Additionally, the following hotkeys are also defined in the board and package
editors.

| Keystroke     | Action                                        |
| ------------- | --------------------------------------------- |
| Ctrl+R        | Switch to AIRWIRE visibility preset           |
| Ctrl+T        | Switch to CONCISE\_TOP visibility preset      |
| Ctrl+B        | Switch to CONCISE\_BOTTOM visibility preset   |
| Ctrl+A        | Switch to CONCISE\_ALL visibility preset      |
| Ctrl+Shift+T  | Switch to DETAILED\_TOP visibility preset     |
| Ctrl+Shift+B  | Switch to DETAILED\_BOTTOM visibility preset  |
| Ctrl+Shift+A  | Switch to DETAILED\_ALL visibility preset     |
| Ctrl+F        | Fill up copper polygons and update airwires   |
| Ctrl+E        | Empty out copper polygons                     |

# Requirements

The following software must be installed on your system in order to clone and
use these scripts.

- [Eagle][eagle-install]
- [Git][git-install]

Depending on your needs, you might want to purchase a suitable Eagle license as
the free version in the above link offers only limited functionality.

# Usage

Carry out the following steps to set up Eagle to use these scripts.

- Open a terminal if you're on a Linux machine or Git Bash if you're using
  Windows. Enter the directory where you wish to clone this repository.

  ```
  cd <path>
  ```

  For example, if you wish to clone the repository in your desktop folder, you
  would type one of the following commands.

  ```
  cd /home/<username>/Desktop     # Linux
  cd C:/Users/<username>/Desktop  # Windows
  ```

  Note that Git Bash uses forward slashes to separate directories in the path
  although Windows uses backslashes.

- If you are not inside another Git repository, simply clone this repository by
  running the following command.

  ```
  git clone https://github.com/Kenneth-Goveas/Eagle-Scripts.git
  ```

  If, on the other hand, you wish to clone this repository inside another Git
  repository, it is best to add it as a submodule.

  ```
  git submodule add https://github.com/Kenneth-Goveas/Eagle-Scripts.git
  ```

- Open Eagle and click on *Options > Directories*. Fill in the path to your copy
  of this repository into the *Scripts* field and click *OK*. For example, if
  you cloned this library in your desktop folder, the path would be one of the
  following.

  ```
  /home/<username>/Desktop/Eagle-Scripts      # Linux
  C:\Users\<username>\Desktop\Eagle-Scripts   # Windows
  ```

  Note that this time, you must use backslashes if you're on a Windows system.

If the above three steps were carried out successfully, Eagle has been
configured to automatically load the scripts on startup.

[eagle-home]:     https://www.autodesk.com/products/eagle
[eagle-install]:  https://www.autodesk.com/products/eagle/free-download
[git-install]:    https://git-scm.com/downloads
