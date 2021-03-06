# SQLiteGlue-core

Low-level Android &amp; other Java native glue interface to sqlite using Gluegen.

Unlicense (public domain).

## About

SQLiteGlue provides the basic low-level functions necessary to use sqlite from an Android or other
Java application over JNI (Java native interface). This is accomplished by using
[GlueGen](http://jogamp.org/gluegen/www/) around a simple wrapper C module.

This project is meant to help build a higher-level sqlite interface library, with the JNI layer completely isolated and may be embedded with the package name changed.

**NOTE:** This project references the `gluegentools` and `sqlite-amalgamation` subprojects, which are resolved by: $ `make init` (as described below).

**WARNING:** The sqlite database and statement handles that are returned by the `SQLiteGlue` library functions are raw C pointer values (with `0x100000000` added). If someone uses a sqlite database or statement handle that is not valid, or no longer valid with the `SQLiteGlue` library the behavior is undefined (a crash, for example). It is *NOT* recommended to use this API directly unless you really understand how this library works internally.

TBD API and some internal details (probably in a blog post)

# Building

## Normal build

Initialize with the `gluegentools` and `sqlite-amalgamation` subprojects:

$ `make init`

Then to build:

$ `make`

## Regenerage Java & C glue code

$ `make regen`

# Testing

Test Android app in: https://github.com/sqlg/SQLiteGlue-test-Android

