# PopCAM

This command line tool provides a simple way to turn Eagle .brd files into pick and place gcodes for use with a [RetroPopulator](http://hackaday.io/project/1605) pick and place retrofit.

PopCAM currently supports OSX and Linux. It should be possible to install PopCAM on Windows however I haven't tried it yet. Note: the install instructions are specific to Linux and OSX.


## Installation (OSX and Linux)

### Dependencies

There are no packages for PopCAM at this time (if you build one let me know!).
So before you install PopCAM you will need to install the following first:

1. Ruby (1.8 or higher, this should be pre-installed on OSX)
2. Bundler (run `gem install bundler`)

### Download and Install

Run the following in your command line from the directory where you want to install PopCAM:

1. `curl -L https://github.com/D1plo1d/PopCAM/archive/master.zip | tar -zx`
2. `./PopCAM-master/scripts/install.rb`


## Useage

### 1. Adding a .yml file

This is where it gets a bit tricky (mainly because PopCAM is very much a work
in progress). To convert your .brd file to gcode your going to need to create a
.yml file with the same name as your .brd file in the same directory.

For example if your .brd file is `./test_123.brd` your .yml file should be `./test_123.yml`

The best way to do this is to copy the contents of [HeartSparkBar_V2p0.yml](https://raw.githubusercontent.com/D1plo1d/PopCAM/master/examples/HeartSparkBar_V2p0.yml) into your new .yml file.

Once you've got that done you'll want to modify the file to include all the settings for your particular brd and jig setup. The example file contains documentation on how to use its various settings.

### 2. Running PopCAM

Once you've got your .yml file setup run `popcam MY_BRD_FILE.brd` and PopCAM will create your gcode file

eg. `popcam ./test_123.brd` will take `test_123.brd` and `test_123.yml` and create `test_123.gcode`

## License

GPL3
