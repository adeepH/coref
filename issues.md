## Some common issues
1. The project requires tensorflow v1, which is very much outdated. Recommend rewrite to upgrade to tf 2
1. If you need to run it regardless make sure python version is 3.6 or 3.7, can use conda to create a new venv with python=3.7
1. Try to install requirements one by one trhough conda in a new venv instead of pip'ing the requirements.txt
1. warning: "_GLIBCXX_USE_CXX11_ABI" redefined => there was a problem when compiling tf 1.14 on cuda 11 (in the server). this is my undertanding of the issue. reinforces my belief to port to tf2
1. Disregrard earlier entires, use python 3.5, there are no issues when installing requirements.txt
1. setup_all.sh runs without any issues - can proceed further
1. Lot of depricated warnings. Would be better in the long run to make changes

## Final result
`2023-03-06 19:11:44.027994: I tensorflow/stream_executor/platform/default/dso_loader.cc:53] Could not dlopen library 'libcuda.so.1'; dlerror: libcuda.so.1: cannot open shared object file: No such file or directory; LD_LIBRARY_PATH: /N/soft/rhel7/intel/19.5/compilers_and_libraries_2019.5.281/linux/compiler/lib/intel64:/N/soft/rhel7/intel/19.5/compilers_and_libraries_2019.5.281/linux/ipp/lib/intel64:/N/soft/rhel7/intel/19.5/compilers_and_libraries_2019.5.281/linux/compiler/lib/intel64_lin:/N/soft/rhel7/intel/19.5/compilers_and_libraries_2019.5.281/linux/mkl/lib/intel64_lin:/N/soft/rhel7/intel/19.5/compilers_and_libraries_2019.5.281/linux/tbb/lib/intel64/gcc4.7:/N/soft/rhel7/intel/19.5/debugger_2019/iga/lib:/N/soft/rhel7/intel/19.5/debugger_2019/libipt/intel64/lib:/N/soft/rhel7/intel/19.5/compilers_and_libraries_2019.5.281/linux/daal/lib/intel64_lin:/N/soft/rhel7/gcc/12.1.0/lib64:/N/soft/rhel7/gcc/12.1.0/lib:/N/soft/rhel7/gcc/infrastructure/lib`
`2023-03-06 19:11:44.037693: E tensorflow/stream_executor/cuda/cuda_driver.cc:318] failed call to cuInit: UNKNOWN ERROR (303)`
`2023-03-06 19:11:44.037752: I tensorflow/stream_executor/cuda/cuda_diagnostics.cc:156] kernel driver does not appear to be running on this host (h1.carbonate.uits.iu.edu): /proc/driver/nvidia/version does not exist`
`2023-03-06 19:11:44.038231: I tensorflow/core/platform/cpu_feature_guard.cc:142] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA`
`2023-03-06 19:11:44.085238: I tensorflow/core/platform/profile_utils/cpu_utils.cc:94] CPU Frequency: 2500275000 Hz`
`2023-03-06 19:11:44.086917: I tensorflow/compiler/xla/service/service.cc:168] XLA service 0x10669f90 executing computations on platform Host. Devices:`
`2023-03-06 19:11:44.086956: I tensorflow/compiler/xla/service/service.cc:175]   StreamExecutor device (0): <undefined>, <undefined>`
`terminate called after throwing an instance of 'std::system_error'`
`  what():  Resource temporarily unavailable`
`Aborted`

Need to see how to actually run cuda code in this env

#### possible fix
use module deeplearning. problem - its not compatible with module conda. we would lose our venv

