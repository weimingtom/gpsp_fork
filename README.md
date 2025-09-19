# gpsp_fork
[WIP] my gpSP fork

## Ref
* https://github.com/zfteam/gpsp
* gpsp-master_v1_v3s_good.tar.gz
* (not good for v3s) https://github.com/notaz/gpsp
* (dead) https://github.com/hsinyuwang/gpsp
* https://bbs.aw-ol.com/topic/3730/t113-tina-linux-移植-gpsp-模拟器
* (android) https://github.com/slp/gameboid
* (not good, for notaz version ubuntu x86) gpsp_v4.tar.gz
* (not good, for hsinyuwang xboy version build) gpsp-main_v2.tar.gz
* X-Boy_20221023.img

## How to build for LiulianPi v3s
* $ cd liulianpi_v3s
* $ make clean
* $ make
* \# SDL_NOMOUSE=1 ./gpsp ./demo.gba
