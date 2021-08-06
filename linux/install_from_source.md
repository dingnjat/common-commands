### Install package from source
1. `sudo apt-get install build-essential`
2. `tar -xzvf file.tar.gz or tar -xjvf file.tar.bz2`
3. `cd /file`
4. `xdg-open INSTALL` (to get instructions of package, usually follow below commands)
5. `mkdir build && cd build`
6. `cmake ../`
7. `make`
8. `sudo make install`
* Use `sudo make clean-all` if build error or have to re-build
* Many libraries often is missing. Have to download manually from Internet.
* TIP: Some missing libraries just need `-dev` in suffix to be found.
