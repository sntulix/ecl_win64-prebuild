#ecl win64 prebuild

# note

* .lisp -> .c -> .exe succeed.
```
    > *features*
    (:WALKER :ECL-BYTECMP :CDR-1 :CDR-5 :WIN32 :FORMATTER :CDR-7 :ECL-WEAK-HASH
    :LITTLE-ENDIAN :LONG-LONG :UINT64-T :UINT32-T :UINT16-T
    :RELATIVE-PACKAGE-NAMES :UNICODE :CLOS-STREAMS :CMU-FORMAT :WINDOWS :MSVC
    :ECL-PDE :DLOPEN :CLOS :THREADS :BOEHM-GC :ANSI-CL :COMMON-LISP
    :IEEE-FLOATING-POINT :CDR-14 :PREFIXED-API :FFI :PENTIUM4 :COMMON :ECL)
```

* build with vs express 2013 update4
* test on VS2015 x86 x64 Cross Tools Command Prompt
* prepare to enable msvc c-compile
```
    (ext:install-c-compiler)
    (setq c::*delete-files* NIL)
    (compile-file "hello.lisp" :system-p t)
    (c:build-program "hello" :lisp-files '("hello.obj"))
```

# references

* http://stibear.hatenablog.com/entry/2016/03/21/220704
* http://d.hatena.ne.jp/eel3/20150307/1425696483
* https://gitlab.com/embeddable-common-lisp/ecl/issues/213
