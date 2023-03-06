#### Some common issues
1. The project requires tensorflow v1, which is very much outdated. Recommend rewrite to upgrade to tf 2
1. If you need to run it regardless make sure python version is 3.6 or 3.7, can use conda to create a new venv with python=3.7
1. Try to install requirements one by one trhough conda in a new venv instead of pip'ing the requirements.txt
1. warning: "_GLIBCXX_USE_CXX11_ABI" redefined => there was a problem when compiling tf 1.14 on cuda 11 (in the server). this is my undertanding of the issue. reinforces my belief to port to tf2
