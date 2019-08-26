# The **Taichi** Programming Language
### High-Performance Computing on Spatially Sparse Data Structures

# Installation
Supports Ubuntu 14.04/16.04/18.04, ArchLinux, Mac OS X. For GPU support, CUDA 9.0+ is needed.

 - Install `taichi` with the [installation script](https://taichi.readthedocs.io/en/latest/installation.html#ubuntu-arch-linux-and-mac-os-x)
 - (Optional) If you use the experimental LLVM backend, make sure you have LLVM 8 built from scratch, with
  ```
  cmake .. -DLLVM_ENABLE_RTTI:BOOL=ON -DBUILD_SHARED_LIBS:BOOL=ON
  ```
 - Execute `ti install https://github.com/yuanming-hu/taichi_lang` to install the DSL project
 - Execute `python3 -m pip install astpretty astor pytest opencv-python`
 - Add the following line to your `~/.bashrc` or `~/.zshrc` for the python frontend.
 ```bash
 export PYTHONPATH=$TAICHI_REPO_DIR/projects/taichi_lang/python:$PYTHONPATH
 ```
 - Execute `ti test` to run all the tests. It may take a around 20 minutes to run all tests.

# Folder Structure
Key folders are
 - *examples* : example programs written in Taichi
   - *cpp*: benchmarking examples in the SIGGRAPH Asia paper (mpm_benchmark.cpp, smoke_renderer.cpp, cnn.cpp)
   - *fem*: the FEM benchmark
 - *include*: language runtime
 - *src*: the compiler implementation (The functionality is briefly documented in each file)
   - *analysis*: static analysis passes
   - *backends*: codegen to x86 and CUDA
   - *transforms*: IR transform passes
   - *ir*: the intermediate representation system
   - *program*: the context for taichi programs
   - ...
 - *test*: unit tests
