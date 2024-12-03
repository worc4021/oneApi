# Install Intel oneAPI toolchain on windows or linux agent

This action allows you to install the Intel oneAPI on github hosted runners. At the moment, the only version we have available is 2025.0.0.822. The installation is built upon the intel [oneapi-ci](https://github.com/oneapi-src/oneapi-ci) repository.

The use is very simple:

```
windows-build:
    runs-on: windows-latest
    steps:
    - uses: worc4021/oneApi@v7
      with:
        icx: true
        ifx: false
        mkl: true
```

After the action has run the worker has all the variables set in its environment.

If you need to install cmake, ninja etc it can sometimes get upset about the path tempering. Use this action first thing and install additonal tools after.