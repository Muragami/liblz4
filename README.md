libLZ4 - 'XIO' LZ4 Library
================================

This is the same library taken from here: [lz4/lz4](https://github.com/lz4/lz4)
Except it has an added lz4io.h and lz4io.c to provide a way to
use the file interface with your own provided XIO structure.

You should be able to just 'make' on your target platform of choice.

#### XIO struct

```C
typedef struct _XIO {
    void *internal;
    size_t (*read)(void * ptr, size_t size, size_t count, void* io);
    size_t (*write)(void * ptr, size_t size, size_t count, void* io);
} XIO;
```
The XIO struct has a void pointer for your own use, and a
read() and write() function that complies with the stdio versions.
Write your read/write to behave as cstdio does, and you are golden.

#### Static linking only

This version has been paired down to provide a static linked
library only.

#### License

All source material within this repo are BSD 2-Clause licensed.
See [LICENSE](LICENSE) for details.
The license is also reminded at the top of each source file.
