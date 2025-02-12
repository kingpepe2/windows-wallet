Tutorial - Compile Windows wallet on Ubuntu Server 22.04
Compile a wallet for Microsoft Windows on Ubuntu Server 22.04 with the following tutorial.

Update your Ubuntu server with the following command:

sudo apt-get update && sudo apt-get upgrade -y

Install the required dependencies with the following command:

sudo apt-get install make automake cmake curl g++-multilib libtool binutils-gold bsdmainutils pkg-config python3 patch bison -y

Create your source code directory with the following commands:

cd ~/
mkdir source_code
cd source_code

Download the source code of your coin with the following command:

wget "https://dl.walletbuilders.com/download?customer=b99a53a3f81f1bbb2049773ab7e188c73b503cc19256b64eb5&filename=kingpepe-source.tar.gz" -O kingpepe-source.tar.gz

Type the following command to extract the tar file:

tar -xzvf kingpepe-source.tar.gz

64-bit

Install the required dependencies with the following command:

sudo apt-get install g++-mingw-w64-x86-64 -y

Set the default x86_64-w64-mingw32-g++ compiler option to posix with the following command:

sudo update-alternatives --set x86_64-w64-mingw32-g++ /usr/bin/x86_64-w64-mingw32-g++-posix

Build x86_64-w64-mingw32 with the following commands:

PATH=$(echo "$PATH" | sed -e 's/:\/mnt.*//g')
cd depends
make HOST=x86_64-w64-mingw32
cd ..

Type the following commands to compile your 64 bit wallet for Microsoft Windows.

./autogen.sh
CONFIG_SITE=$PWD/depends/x86_64-w64-mingw32/share/config.site ./configure --prefix=/
make

The compiled wallet for Microsoft Windows is located in the directory src/qt, the tools are located in the directory src.
