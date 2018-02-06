## Laboratory work XV

Данная лабораторная работа посвещена изучению инструментов статического и динамического анализа кода
```ShellSession
$ open http://cppcheck.sourceforge.net
```
Исходный код имеет вид(test.cpp)
```cpp
// Copyright (c) 2018 Igor Kulikov
#include <iostream>

int main() {
    int bbb = 20;
    int ccc = 13;
    int sum = bbb + ccc;
    std::cout << "sum= " << sum << std::endl;

    return 0;
}
```

Анализируем исходный код с помощью cpplint:
```
Done processing test.cpp
```

Анализируем исходный код с помощью cppcheck:
```
Checking test.cpp...
```

Анализируем исходный код с помощью oclint:
```
OCLint Report

Summary: TotalFiles=1 FilesWithViolations=0 P1=0 P2=0 P3=0 


[OCLint (http://oclint.org) v0.13]
```

Анализируем исходный код с помощью valgrind:
```
==11458== Memcheck, a memory error detector
==11458== Copyright (C) 2002-2015, and GNU GPL'd, by Julian Seward et al.
==11458== Using Valgrind-3.11.0 and LibVEX; rerun with -h for copyright info
==11458== Command: ./a.out
==11458== 
--11458-- Valgrind options:
--11458--    --leak-check=yes
--11458--    -v
--11458-- Contents of /proc/version:
--11458--   Linux version 4.10.0-28-generic (buildd@lgw01-12) (gcc version 5.4.0 20160609 (Ubuntu 5.4.0-6ubuntu1~16.04.4) ) #32~16.04.2-Ubuntu SMP Thu Jul 20 10:19:48 UTC 2017
--11458-- 
--11458-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2
--11458-- Page sizes: currently 4096, max supported 4096
--11458-- Valgrind library directory: /usr/lib/valgrind
--11458-- Reading syms from /home/goga/ZolbergNLAB/a.out
--11458-- Reading syms from /lib/x86_64-linux-gnu/ld-2.23.so
--11458--   Considering /lib/x86_64-linux-gnu/ld-2.23.so ..
--11458--   .. CRC mismatch (computed 9bc477cd wanted 3da2f12a)
--11458--   Considering /usr/lib/debug/lib/x86_64-linux-gnu/ld-2.23.so ..
--11458--   .. CRC is valid
--11458-- Reading syms from /usr/lib/valgrind/memcheck-amd64-linux
--11458--   Considering /usr/lib/valgrind/memcheck-amd64-linux ..
--11458--   .. CRC mismatch (computed eea41ea9 wanted 2009db78)
--11458--    object doesn't have a symbol table
--11458--    object doesn't have a dynamic symbol table
--11458-- Scheduler: using generic scheduler lock implementation.
--11458-- Reading suppressions file: /usr/lib/valgrind/default.supp
==11458== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-11458-by-goga-on-???
==11458== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-11458-by-goga-on-???
==11458== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-11458-by-goga-on-???
==11458== 
==11458== TO CONTROL THIS PROCESS USING vgdb (which you probably
==11458== don't want to do, unless you know exactly what you're doing,
==11458== or are doing some strange experiment):
==11458==   /usr/lib/valgrind/../../bin/vgdb --pid=11458 ...command...
==11458== 
==11458== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==11458==   /path/to/gdb ./a.out
==11458== and then give GDB the following command
==11458==   target remote | /usr/lib/valgrind/../../bin/vgdb --pid=11458
==11458== --pid is optional if only one valgrind process is running
==11458== 
--11458-- REDIR: 0x401cf90 (ld-linux-x86-64.so.2:strlen) redirected to 0x3809e181 (???)
--11458-- Reading syms from /usr/lib/valgrind/vgpreload_core-amd64-linux.so
--11458--   Considering /usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--11458--   .. CRC mismatch (computed 2567ccf6 wanted 49420590)
--11458--    object doesn't have a symbol table
--11458-- Reading syms from /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so
--11458--   Considering /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--11458--   .. CRC mismatch (computed 0e27c9a8 wanted ac585421)
--11458--    object doesn't have a symbol table
==11458== WARNING: new redirection conflicts with existing -- ignoring it
--11458--     old: 0x0401cf90 (strlen              ) R-> (0000.0) 0x3809e181 ???
--11458--     new: 0x0401cf90 (strlen              ) R-> (2007.0) 0x04c31020 strlen
--11458-- REDIR: 0x401b8e0 (ld-linux-x86-64.so.2:index) redirected to 0x4c30bc0 (index)
--11458-- REDIR: 0x401bb00 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4c320d0 (strcmp)
--11458-- REDIR: 0x401dcf0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x4c35270 (mempcpy)
--11458-- Reading syms from /usr/lib/x86_64-linux-gnu/libstdc++.so.6.0.21
--11458--   Considering /usr/lib/x86_64-linux-gnu/libstdc++.so.6.0.21 ..
--11458--   .. CRC mismatch (computed 2f26e592 wanted a874dadb)
--11458--    object doesn't have a symbol table
--11458-- Reading syms from /lib/x86_64-linux-gnu/libm-2.23.so
--11458--   Considering /lib/x86_64-linux-gnu/libm-2.23.so ..
--11458--   .. CRC mismatch (computed 8bd88005 wanted 32b88176)
--11458--   Considering /usr/lib/debug/lib/x86_64-linux-gnu/libm-2.23.so ..
--11458--   .. CRC is valid
--11458-- Reading syms from /lib/x86_64-linux-gnu/libgcc_s.so.1
--11458--   Considering /lib/x86_64-linux-gnu/libgcc_s.so.1 ..
--11458--   .. CRC mismatch (computed b9a68419 wanted 29d51b00)
--11458--    object doesn't have a symbol table
--11458-- Reading syms from /lib/x86_64-linux-gnu/libc-2.23.so
--11458--   Considering /lib/x86_64-linux-gnu/libc-2.23.so ..
--11458--   .. CRC mismatch (computed b2979fac wanted 1affc958)
--11458--   Considering /usr/lib/debug/lib/x86_64-linux-gnu/libc-2.23.so ..
--11458--   .. CRC is valid
--11458-- REDIR: 0x576aa00 (libc.so.6:strcasecmp) redirected to 0x4a286f0 (_vgnU_ifunc_wrapper)
--11458-- REDIR: 0x5766280 (libc.so.6:strcspn) redirected to 0x4a286f0 (_vgnU_ifunc_wrapper)
--11458-- REDIR: 0x576ccf0 (libc.so.6:strncasecmp) redirected to 0x4a286f0 (_vgnU_ifunc_wrapper)
--11458-- REDIR: 0x57686f0 (libc.so.6:strpbrk) redirected to 0x4a286f0 (_vgnU_ifunc_wrapper)
--11458-- REDIR: 0x5768a80 (libc.so.6:strspn) redirected to 0x4a286f0 (_vgnU_ifunc_wrapper)
--11458-- REDIR: 0x576a14b (libc.so.6:memcpy@GLIBC_2.2.5) redirected to 0x4a286f0 (_vgnU_ifunc_wrapper)
--11458-- REDIR: 0x5768400 (libc.so.6:rindex) redirected to 0x4c308a0 (rindex)
--11458-- REDIR: 0x575f130 (libc.so.6:malloc) redirected to 0x4c2db20 (malloc)
--11458-- REDIR: 0x5766720 (libc.so.6:strlen) redirected to 0x4c30f60 (strlen)
--11458-- REDIR: 0x5769bf0 (libc.so.6:__GI_memcmp) redirected to 0x4c33b90 (__GI_memcmp)
--11458-- REDIR: 0x5764cd0 (libc.so.6:strcmp) redirected to 0x4a286f0 (_vgnU_ifunc_wrapper)
--11458-- REDIR: 0x577a570 (libc.so.6:__strcmp_sse2_unaligned) redirected to 0x4c31f90 (strcmp)
--11458-- REDIR: 0x5769bb0 (libc.so.6:bcmp) redirected to 0x4a286f0 (_vgnU_ifunc_wrapper)
--11458-- REDIR: 0x58493f0 (libc.so.6:__memcmp_sse4_1) redirected to 0x4c33cd0 (__memcmp_sse4_1)
--11458-- REDIR: 0x576a3b0 (libc.so.6:__GI_mempcpy) redirected to 0x4c34fa0 (__GI_mempcpy)
sum= 33
--11458-- REDIR: 0x575f4f0 (libc.so.6:free) redirected to 0x4c2ed80 (free)
==11458== 
==11458== HEAP SUMMARY:
==11458==     in use at exit: 72,704 bytes in 1 blocks
==11458==   total heap usage: 2 allocs, 1 frees, 73,728 bytes allocated
==11458== 
==11458== Searching for pointers to 1 not-freed blocks
==11458== Checked 115,384 bytes
==11458== 
==11458== LEAK SUMMARY:
==11458==    definitely lost: 0 bytes in 0 blocks
==11458==    indirectly lost: 0 bytes in 0 blocks
==11458==      possibly lost: 0 bytes in 0 blocks
==11458==    still reachable: 72,704 bytes in 1 blocks
==11458==         suppressed: 0 bytes in 0 blocks
==11458== Reachable blocks (those to which a pointer was found) are not shown.
==11458== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==11458== 
==11458== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
==11458== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
```

## Tasks

- [X] 1. Ознакомиться со ссылками учебного материала
- [X] 2. Используя **cpplint** провести анализ проекта на **C++**
- [X] 3. Используя **Cppcheck** провести анализ проекта на **C++**
- [X] 4. Используя **OCLint** провести анализ проекта на **C++**
- [X] 5. Используя **Valgrind** провести анализ проекта на **C++**
- [X] 6. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Links

- [Google C++ Style Guide](https://github.com/cpplint/cpplint)
- [Cppcheck Manual](http://cppcheck.sourceforge.net/manual.pdf)
- [Valgrind Quick Start Guide](http://valgrind.org/docs/manual/index.html)
- [OCLint Tutorial](http://docs.oclint.org/en/stable/intro/tutorial.html)

```
Copyright (c) 2017 Братья Вершинины
```