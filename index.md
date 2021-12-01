Simple Device Model (SDM) is an open source instrument control and data acquisition framework for Windows and Linux. It provides interactive GUI tools for operating devices and visualizing the received data. It is also fully scriptable with [Lua](https://www.lua.org).

A device is represented by SDM as a set of control channels and data sources, hence the “model”. SDM interacts with devices by writing and reading registers and memory blocks in the device’s virtual address space, and by reading data streams from the device. The actual code that communicates with hardware is encapsulated within a **plugin**. SDM framework is [well documented](#documentation) and includes an SDK which contains headers and libraries to develop plugins in C and C++ as well as a few example plugins.

SDM was created to make hardware engineers' life easier by reducing the amount of coding necessary to get the device up and running. SDM is most useful for prototyping, allowing the developer to quickly create virtual control panels and dashboards. Scriptability makes it also well suited for test and measurement automation.

## Screenshots

SDM provides multiple methods of data visualization, such as 2D plot (oscillogram), bar chart, scrolling image and binary representations.

<p align="center"><a href="https://simpledevicemodel.github.io/assets/mainwindow.png" title="Click to enlarge"><img alt="sdmconsole main window screenshot" src="/assets/mainwindow.png"></a></p>

Register map provides access to the device’s virtual address space. Values can be entered directly or with the help of drop-down lists, combo boxes and push buttons. Register map tables are fully editable in GUI.

<p align="center"><a href="https://simpledevicemodel.github.io/assets/registers2.png" title="Click to enlarge"><img alt="sdmconsole register map screenshots" src="/assets/registers2.png"></a></p>

## Download

The latest release, 1.0.0, was published on 2021-11-23.

* [**SDM-1.0.0-setup-x64.exe**](https://github.com/SimpleDeviceModel/sdm/releases/download/1.0.0/SDM-1.0.0-setup-x64.exe) - for 64-bit Windows
* [**SDM-1.0.0-setup-x86.exe**](https://github.com/SimpleDeviceModel/sdm/releases/download/1.0.0/SDM-1.0.0-setup-x86.exe) - for 32-bit Windows
* [**SDM-1.0.0-src.tar.gz**](https://github.com/SimpleDeviceModel/sdm/releases/download/1.0.0/SDM-1.0.0-src.tar.gz) - sources (multi-platform)

## Building

Building SDM from source requires [CMake](https://cmake.org) and [Qt5](https://www.qt.io). For Ubuntu, the prerequisites can be installed as follows:

```
sudo apt install build-essential qtbase5-dev qtbase5-dev-tools libqt5svg5-dev qttools5-dev \
qttools5-dev-tools qttranslations5-l10n qt5-image-formats-plugins cmake
```

Then, the SDM framework can be built:

```
wget https://github.com/SimpleDeviceModel/sdm/releases/download/1.0.0/SDM-1.0.0-src.tar.gz
tar -xzf SDM-1.0.0-src.tar.gz
cd SDM-1.0.0-src
mkdir build
cd build
cmake ../src
make -j
sudo make install
```

By default, SDM will be installed to `/usr/local`. Refer to [the manual (PDF)](https://github.com/SimpleDeviceModel/sdm/raw/master/doc/manual.pdf) for detailed build instructions.

Windows builds of SDM were linked against [Qt 5.6.3](https://github.com/SimpleDeviceModel/sdm/releases/download/1.0.0/qt-everywhere-opensource-src-5.6.3.7z). Other versions of Qt can be downloaded from the [Qt website](https://download.qt.io/).

## Documentation

* [**User Manual (PDF)**](https://github.com/SimpleDeviceModel/sdm/raw/master/doc/manual.pdf)

Examples shipped with the SDM framework:

* `uartdemo` - an example plugin communicating with an [Arduino Uno](https://www.arduino.cc/) board over the serial port.
* `testplugin` - a purely software plugin to help you get acquainted with the program interface (no extra hardware required).

## License

Simple Device Model framework is Copyright © [Microproject LLC](http://www.micro-project.ru/en/), 2015-2021.

Simple Device Model framework is licensed under the terms of the GNU Lesser General Public License, either version 3 of the License, or (at your option) any later version. The SDK is licensed under the terms of the MIT license. See [license.txt](https://raw.githubusercontent.com/SimpleDeviceModel/sdm/master/doc/licenses/license.txt) for details.
