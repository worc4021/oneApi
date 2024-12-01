# Install Intel oneAPI toolchain on windows agent

This action allows you to install the Intel oneAPI on github hosted runners. At the moment, the only version we have available is 2025.0.0.822. The installation is built upon the intel [oneapi-ci](https://github.com/oneapi-src/oneapi-ci) repository.

The use is very simple:

```
windows-build:
    runs-on: windows-latest
    steps:
    - uses: worc4021/oneApi@v1
```

After the action has run the worker has all the variables set in its environment.

If you require more than just the intel compiler, then pick the tool in question [here](https://oneapi-src.github.io/oneapi-ci/) and list them separated by `:`, e.g. to install the icx as well as the ifx compiler use:


```
windows-build:
    runs-on: windows-latest
    steps:
    - uses: worc4021/oneApi@v1
      with:
        WINDOWS_CPP_COMPONENTS: intel.oneapi.win.cpp-dpcpp-common:intel.oneapi.win.ifort-compiler
```