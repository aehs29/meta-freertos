# meta-freertos
FreeRTOS distro layer compatible with OpenEmbedded

## Build Status

|  master 	| [![Build Status](https://dev.azure.com/aehs291/freertos-layer/_apis/build/status/aehs29.meta-freertos?branchName=master)](https://dev.azure.com/aehs291/freertos-layer/_build/latest?definitionId=1&branchName=master)  	|
|:-:	|---	|
| warrior  	|  [![Build Status](https://dev.azure.com/aehs291/freertos-layer/_apis/build/status/aehs29.meta-freertos?branchName=warrior)](https://dev.azure.com/aehs291/freertos-layer/_build/latest?definitionId=1&branchName=warrior) 	|

## Dependencies

This layer depends on:

     URI: git://git.yoctoproject.org/poky
     branch: master


## License
This layer has an MIT license (see LICENSE) and it fetches code from FreeRTOS that has its own License
(MIT as of today), along with code taken from [jkovacic](https://github.com/jkovacic/FreeRTOS-GCC-ARM926ejs) which also has its own license.


## Building a FreeRTOS application

1.- Clone this layer along with the specified layers

2.- $ source oe-init-build-env

3.- Add this layer to BBLAYERS on conf/bblayers.conf

4.- Add the following to your conf/local.conf:

```
DISTRO = "poky-freertos"

MACHINE = "qemuarmv5" # It is the only one supported at the moment
```

5.- Build an example application:

```
$ bitbake freertos-demo
```
6.- Run the application on QEMU:
```
$ runqemu
```
You should be able to see the output of the application on QEMU and interact with it.
