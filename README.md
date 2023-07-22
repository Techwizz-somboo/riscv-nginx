# nginx for RISC-V

nginx tree with changes needed for cross-compiling to 64-bit RISC-V.

## Usage

```
./auto/configure \
--with-cc-opt="-DAO_USE_PTHREAD_DEFS=1 -DNGX_HAVE_MAP_ANON=1 -DNGX_HAVE_LIBATOMIC=1 -DNGX_SYS_NERR=150 -Isrc/libatomic_ops" \
--with-libatomic \
--with-ld-opt="-lpthread" \
--with-ld-opt="-lcrypt"

make
```
