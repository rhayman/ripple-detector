# Ripple Detector

![ripple-detector-screenshot](https://open-ephys.github.io/gui-docs/_images/rippledetector-01.png)

Open Ephys GUI plugin for ripple detection. It contains an embedded mechanism based on EMG or accelerometer data that blocks ripple events when movement is detected. 

## Installation

The plugin can be added via the Open Ephys GUI's built-in Plugin Installer. Press **ctrl-P** or **⌘P** to open the Plugin Installer, browse to "Ripple Detector", and click the "Install" button. The Ripple Detector plugin should now be available to use.

## Usage

Instructions for using the Ripple Detector plugin are available [here](https://open-ephys.github.io/gui-docs/User-Manual/Plugins/Ripple-Detector.html).

## Building from source

First, follow the instructions on [this page](https://open-ephys.github.io/gui-docs/Developer-Guide/Compiling-the-GUI.html) to build the Open Ephys GUI.

Then, clone this repository into a directory at the same level as the `plugin-GUI`, e.g.:
 
```
Code
├── plugin-GUI
│   ├── Build
│   ├── Source
│   └── ...
├── OEPlugins
│   └── ripple-detector
│       ├── Build
│       ├── Source
│       └── ...
```

### Windows

**Requirements:** [Visual Studio](https://visualstudio.microsoft.com/) and [CMake](https://cmake.org/install/)

From the `Build` directory, enter:

```bash
cmake -G "Visual Studio 17 2022" -A x64 ..
```

Next, launch Visual Studio and open the `OE_PLUGIN_ripple-detector.sln` file that was just created. Select the appropriate configuration (Debug/Release) and build the solution.

Selecting the `INSTALL` project and manually building it will copy the `.dll` and any other required files into the GUI's `plugins` directory. The next time you launch the GUI from Visual Studio, the Ripple Detector plugin should be available.


### Linux

**Requirements:** [CMake](https://cmake.org/install/)

From the `Build` directory, enter:

```bash
cmake -G "Unix Makefiles" ..
make install
```

This will build the plugin and copy the `.so` file into the GUI's `plugins` directory. The next time you launch the GUI compiled version of the GUI, the Ripple Detector plugin should be available.


### macOS

**Requirements:** [Xcode](https://developer.apple.com/xcode/) and [CMake](https://cmake.org/install/)

From the `Build` directory, enter:

```bash
cmake -G "Xcode" ..
```

Next, launch Xcode and open the `ttl-panels.xcodeproj` file that now lives in the “Build” directory.

Running the `ALL_BUILD` scheme will compile the plugin; running the `INSTALL` scheme will install the `.bundle` file to `/Users/<username>/Library/Application Support/open-ephys/plugins-api8`. The TTL Toggle Panel and TTL Display Panel plugins should be available the next time you launch the GUI from Xcode.

## Attribution

If you want to cite the ripple detector or know more about it, please refer to the paper below:

https://iopscience.iop.org/article/10.1088/1741-2552/ac857b

## References

Drieu, C., Todorova, R., & Zugaro, M. (2018a). Nested sequences of hippocampal assemblies during behavior support subsequent sleep replay. Science (New York, N.Y.), 362(6415), 675–679. https://doi.org/10.1126/science.aat2952

Drieu, C., Todorova, R., & Zugaro, M. (2018b). Bilateral recordings from dorsal hippocampal area CA1 from rats transported on a model train and sleeping. CRCNS.org. http://dx.doi.org/10.6080/K0Z899MM.

