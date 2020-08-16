# Getting started
This repo is intended as a gentle introduction to OpenCL, as such it does not have any build scripts because if you are just starting then getting everything to build correctly is the hardest part. I recommend trying to run `devices.c` first which prints out all the CPUs and GPUs available on your system.

## building devices.c (Mac, using clang)
 - clone this repo (or copy the contents of `devices.c` into a file)
   ```git clone https://github.com/metakuna/opencl-snippets```
 - make sure you have clang installed 

## What's the point of this repo
 - a getting started guide for OpenCl
 - a simple build system for testing out kernels
 - a collection of 'standard examples'
    - print device info
    - matrix multiplication
    - image loading etc