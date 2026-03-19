# musl-i386

## problem
```bash
$ ldd pico
        linux-gate.so.1 (0xf7f0f000)
        libc.musl-x86.so.1 => not found

$ readelf -l pico | grep interpreter
      [Requesting program interpreter: /lib/ld-musl-i386.so.1]

$ gdb -q pico
Reading symbols from pico...
(No debugging symbols found in pico)
(gdb) run
Starting program: /home/xxx/data/pico
/bin/bash: line 1: /home/xxx/data/pico: cannot execute: required file not found
During startup program exited with code 127.
```

## solver
```bash
$ echo "cat /lib/libc.musl-x86.so.1; exit" | nc [host] [port] > libc.musl-x86.so.1
$ sudo mv libc.musl-x86.so.1 /lib/
$ sudo chown root:root /lib/libc.musl-x86.so.1
$ sudo chmod 644 /lib/libc.musl-x86.so.1

$ echo "cat /lib/ld-musl-i386.so.1; exit" | nc [host] [port] > ld-musl-i386.so.1
$ sudo mv ld-musl-i386.so.1 /lib/
$ sudo chown root:root /lib/ld-musl-i386.so.1
$ sudo chmod 755 /lib/ld-musl-i386.so.1
```
