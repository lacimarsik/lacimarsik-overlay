# lacimarsik-overlay
Various patches and improvements on Gentoo Linux ebuilds

## sbsigntool ebuild
`app-crypt/sbsigntool-0.6.r2` from overlay differs from upstream `app-crypt/sbsigntool-0.6.r1` by depending on `binutils-libs`. Header file `bfd.h` was required in the compile phase, originally provided by `binutils` now moved to `bunutils-libs`. Log:

```
checking bfd.h usability... no
checking bfd.h presence... no
checking for bfd.h... no
configure: error: bfd.h not found.
bfd.h is usually distributed in a binutils development package.

```
