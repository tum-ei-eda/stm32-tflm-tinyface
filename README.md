# TinyFace Example

This example will attempt to deploy TinyFace on an STM32-F7. Based on the work of [Philipp van Kempen](https://github.com/philippvK).

You may also be interested in our wrapper repository [stm32-tflm-demos](https://github.com/PhilippvK/stm32-tflm-demos) for further details.

## Build
### Project configuration

First configure your board and features like CMSIS-NN, Benchmarking,... as explained [here](https://github.com/PhilippvK/stm32-tflm-demos/blob/master/docs/Usage.md).

Finally, simply run:
```
mkdir build
cd build
cmake -DTF_COMMIT=37c2bf5016fcbed261476386eced503e907cdc01 ..
make
make flash
```
For more details about build instruction, see the [main README](https://github.com/PhilippvK/stm32-tflm-demos/blob/master/README.md).

Other make targets we provide include `make debug` and `make convert` (to convert the `*.tflite` file into [tfite_micro_compiler](https://github.com/tum-ei-eda/tflite_micro_compiler) sources).

### Rebuilding the project
It is mandatory to delete `CMakeCache.txt` after changing the STM32 board. Sometimes, you need to delete the `_deps` folder under `build` before running `cmake ..` again.
