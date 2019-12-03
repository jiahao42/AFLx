## build xmllint

```bash
wget ftp://xmlsoft.org/libxml2/libxml2-git-snapshot.tar.gz
gzip -d libxml2-git-snapshot.tar.gz
tar xf libxml2-git-snapshot.tar
cd libxml2-2.9.7
CC=/home/jiahao/AFLx/afl-gcc CXX=/home/jiahao/AFLx/afl-g++ ./configure --enable-static=no --enable-shared=no && make # edit the absolute path
cd ..
./afl-fuzz -i ./testcases/others/xml -o output -m none ./libxml2-2.9.7/xmllint @@
```

