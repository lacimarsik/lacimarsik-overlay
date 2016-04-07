# lacimarsik-overlay
Various patches and improvements on Gentoo Linux ebuilds

## sbsigntool ebuild
*Note: as of 04-03-2016 the fix was pushed upstream, so no need to overlay:* https://bugs.gentoo.org/show_bug.cgi?id=575380

`app-crypt/sbsigntool-0.6.r1` from overlay differs from upstream `app-crypt/sbsigntool-0.6.r1` by depending on `binutils-libs`. Header file `bfd.h` was required in the compile phase, originally provided by `binutils` now moved to `bunutils-libs`. Log:

```
checking bfd.h usability... no
checking bfd.h presence... no
checking for bfd.h... no
configure: error: bfd.h not found.
bfd.h is usually distributed in a binutils development package.

```

