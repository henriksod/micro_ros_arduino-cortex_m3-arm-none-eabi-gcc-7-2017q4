![banner](.images/banner-dark-theme.png#gh-dark-mode-only)
![banner](.images/banner-light-theme.png#gh-light-mode-only)

# Fork of micro-ROS for Arduino v2.0.7-humble

Specifically for cortex-m3 pre-compiled with arm-none-eabi-gcc-7-2017q4.

It is intended to work with a custom platform `per1234:sam` which solves [compiling for SAM on aarch64](https://github.com/arduino/arduino-cli/issues/1339).
https://per1234.github.io/ArduinoCore-sam/package_per1234_samarm64_index.json

In practice, what this solves is that you will be able to compile and upload to Arduino DUE via a Raspberry PI 4 model B running 64 bit Raspberry PI OS.

As a result from this issue:
https://github.com/micro-ROS/micro_ros_arduino/issues/1479

I have intentionally removed all boards except the Arduino Due.

**This repository is not meant to be available in arduino library manager!**

## Supported boards

Supported boards are:

| Board                                                                                    | Min version | Contributor                                    | Details | .meta file               |
| ---------------------------------------------------------------------------------------- | ----------- | ---------------------------------------------- | ------- | ------------------------ |
| [Arduino Due](https://store.arduino.cc/arduino-due)                                      | -           | [@lukicdarkoo](https://github.com/lukicdarkoo) |         | `colcon_verylowmem.meta` |

You can find the available precompiled ROS 2 types for messages and services in [available_ros2_types](available_ros2_types).

### Patch SAM

Go inside your Arduino installation and replace `platform.txt`:

```bash
export ARDUINO_PATH=[Your Arduino path]
cd $ARDUINO_PATH/packages/per1234/hardware/sam/1.6.11-arm64/
curl https://raw.githubusercontent.com/henriksod/micro_ros_arduino-cortex_m3-arm-none-eabi-gcc-7-2017q4/iron/extras/patching_boards/platform_arduinocore_sam.txt > platform.txt
```

## Purpose of the Project

This software is not ready for production use. It has neither been developed nor
tested for a specific use case. However, the license conditions of the
applicable Open Source licenses allow you to adapt the software to your needs.
Before using it in a safety relevant setting, make sure that the software
fulfills your requirements and adjust it according to any applicable safety
standards, e.g., ISO 26262.

## License

This repository is open-sourced under the Apache-2.0 license. See the [LICENSE](LICENSE) file for details.

For a list of other open-source components included in this repository,
see the file [3rd-party-licenses.txt](3rd-party-licenses.txt).
