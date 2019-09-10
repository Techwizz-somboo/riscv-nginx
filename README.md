# nginx for RISC-V

nginx tree with changes needed for cross-compiling to 64-bit RISC-V.

## Usage

```
./auto/configure \
--with-cc=`which riscv64-unknown-linux-gnu-gcc` \
--with-cpp=`which riscv64-unknown-linux-gnu-cpp` \
--without-http_rewrite_module \
--without-http_gzip_module \
--with-cc-opt="-DAO_USE_PTHREAD_DEFS=1 -DNGX_HAVE_MAP_ANON=1 -DNGX_HAVE_LIBATOMIC=1 -DNGX_SYS_NERR=150 -Isrc/libatomic_ops" \
--with-libatomic \
--with-ld-opt="-lpthread"

make
```
