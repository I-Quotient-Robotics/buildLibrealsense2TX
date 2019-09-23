# buildLibrealsense2TX
Build librealsense 2.0 library on the NVIDIA Jetson TX Development kit. Jetson TX1 and Jetson TX2. Intel RealSense D400 series cameras.

- TX2 version L4T 28.2 / L4T 28.2.1 (JetPack 3.2.1)
- Librealsense v2.28.0

## Rebuilding the kernel
```bash
$ ./buildPatchedKernel.sh
```

By default, the kernel sources will be erased from the disk after the kernel has been compiled and installed. You will need >3GB of disk space to build the kernel in this manner. Please note that you should do this on a freshly flashed system. In the case when something goes wrong, it may make the system fail and become unresponsive; the only way to recover may be to use JetPack to reflash.

The script has an option to keep the kernel sources and build information:
```bash
$ ./buildPatchedKernel.sh --nocleanup
```

which may prove useful for debugging purposes.

The script is more provided as a guide on how to build a system that supports librealsense2 than as a practical method to generate a new system.

## Install librealsense
To install the librealsense library:
```bash
$ ./installLibrealsense.sh
```

The install script does the following:
 - Install dependencies
 - Applies Jetson specific patches
 - Sets up udev rules so the camera may be used in user space
 - Builds librealsense, tools and demos
 - Installs libraries and executables


## License
MIT License

Copyright (c) 2017-2018 Jetsonhacks 
Portions Copyright (c) 2015-2018 Raffaello Bonghi (jetson_easy)
Portions Copyright (c) 2016 Mehran Maghoumi

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

