
# gcc-8.4 安装

##安装依赖
```
yum install -y gcc gcc-c++ gcc-gnat libgcc libgcc.i686 glibc-devel bison flex texinfo build-essential zlib-devel

```
## 分割tar 

```
split -b 30m  gcc-releases-gcc-8.4.0.tar.gz   gcc-releases-gcc-8.4.0.tar.gz.  
```

## 合并tar 

```
cat  gcc-releases-gcc-8.4.0.tar.gz.a*  gcc-releases-gcc-8.4.0.tar.gz
```

## 编译安装

```
mkdir build && cd build
../configure --prefix=/usr/local/gcc-8.4.0 --enable-checking=release --enable-languages=c,c++ --disable-multilib
//如果make失败,下一次重新make时候删除build目录，在重新建立build
make && make install
```

