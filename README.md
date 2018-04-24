# GcodeEdit
An executable to modify an indicated GCODE file.

## Overview
This initial version works with the Cura slicer software. In subsequent versions, I may add support for other softwares but I would need access to GCODE examples first.

## Syntax
This assumes that you've installed it per the instructions below so that it will be in your path.

```
$ GcodeEdit -t1=190 PathToGcodeFile
# This version will change the extruder's temperature
# setting to 190C.
$ GcodeEdit -info PathToGcodeFile
$ GcodeEdit -dryrun PathToGcodeFile
$ GcodeEdit -dryrun -v PathToGcodeFile
```

The new `dryrun` command will remove all heat-, extrusion- and fan-related activities from the file, allowing your printer to go through the motions without making anything.

## Installation
The installation of this depends upon whether or not you also have a computer based upon the OS X operating system and further, whether or not you already have the Go compiler itself.

### Mac
Here are the instructions for installing this executable if you are on an Apple-based computer.

#### If you just want the executable
```
$ cd /usr/local/bin      # or anywhere that's in your path
$ curl -o GcodeEdit https://github.com/OutsourcedGuru/GcodeEdit/raw/master/bin/GcodeEdit
$ chmod a+x GcodeEdit
```

#### If you have Go installed:

```
$ cd /usr/local/go/bin
$ sudo curl https://github.com/OutsourcedGuru/GcodeEdit/raw/master/bin/GcodeEdit GcodeEdit
$ cd ~/Desktop
$ which GcodeEdit
/usr/local/go/bin/GcodeEdit
$ GcodeEdit -info MyFile.gcode
Slicer:    Cura_SteamEngine 2.3.1
Layers:    239
First:     -6
Temp:      187C

Finished.
```

#### If you have don't have Go installed:

```
$ cd /usr/local/bin
$ sudo curl https://github.com/OutsourcedGuru/GcodeEdit/raw/master/bin/GcodeEdit GcodeEdit
$ cd ~/Desktop
$ which GcodeEdit
/usr/local/GcodeEdit
$ GcodeEdit MyFile.gcode
Slicer:    Cura_SteamEngine 2.3.1
Layers:    239
First:     -6
Temp:      187C

Finished.
```

### Windows or UNIX
Here are the instructions for building this executable if you are on a different operating system.

#### Install Go
The first step is to [install the Go language compiler](https://golang.org).

It's then usual to create a Go working folder under your user's profile.

```
# These two are optional, depending upon whether
# or not you did this during the Go installation
$ mkdir -p ~/go/src
$ cd ~/go/src
$ go get github.com/OutsourcedGuru/GcodeEdit/
```

This should download everything required and build it for you. Assuming that you installed Go correctly earlier and it's in your path, you should then be able to run it as in the instructions above.
