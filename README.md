# Getting started
This repo is intended as a gentle introduction to OpenCL, as such it does not have any build scripts because if you are just starting then getting everything to build correctly is the hardest part. I recommend trying to run `devices.c` first which prints out all the CPUs and GPUs available on your system, skip to `building devices.c` to do this.

## background
To build any C library you need:
 - To include the necessary headers in your code. For OpenCL this is just the file `OpenCL/opencl.h` on mac, or `CL/cl.h` on other platforms
 - To have the folder where these header files live in your compilers include path. On Mac `OpenCL/opencl.h` is in the default include path but in general you can point to an include folder when you compile using ```clang -I/path/to/include/folder some_program.c```
 - The actual compiled library somewhere in your compilers library search path. You can see which folders `clang` is searching in by doing `clang -Xlinker -v` (it will also give you an error but don't worry about it)
 - To link to the compiled library, which we will do with `-framework OpenCL` (on mac at least it's a framework not a library, on other platforms you might do it like `-lOpenCL`)

## building devices.c (Mac, using clang)
 - clone this repo (or copy the contents of `devices.c` into a file)
   ```git clone https://github.com/metakuna/opencl-snippets```
   ```cd opencl-snippets``` move into it
 - make sure you have clang installed by doing `which clang`, it will print its install directory if it finds it
 - OpenCL is installed by default so run
   ```clang devices.c -framework OpenCL```
 - now if you run `./a.out` it should print out the devices you have available, for me this looks like
   ```
    1. Device: Intel(R) Core(TM) i7-9750H CPU @ 2.60GHz
    1.1 Hardware version: OpenCL 1.2
    1.2 Software version: 1.1
    1.3 OpenCL C version: OpenCL C 1.2
    1.4 Parallel compute units: 12
    2. Device: Intel(R) UHD Graphics 630
    2.1 Hardware version: OpenCL 1.2
    2.2 Software version: 1.2(May 26 2020 20:51:24)
    2.3 OpenCL C version: OpenCL C 1.2
    2.4 Parallel compute units: 24
    3. Device: AMD Radeon Pro 5300M Compute Engine
    3.1 Hardware version: OpenCL 1.2
    3.2 Software version: 1.2 (May 26 2020 20:46:32)
    3.3 OpenCL C version: OpenCL C 1.2
    3.4 Parallel compute units: 20
    ```