# lacimarsik-overlay
Various patches and improvements on Gentoo Linux ebuilds

## ladish ebuild
*Note: 06-04-2016 there is another overlay with a more up-to-date ebuilds here:* https://github.com/tokiclover/bar-overlay/

`media-sound/ladish-9999-r1` from this overlay differs from proaudio overlay version by adding necessary `PYTHON_REQ_USE='threads(+)'` (configure-phase error) and `append-cxxflags '-std=c++11'` (compile-phase error). This is to mirror the changes in new glibmm.

## sbsigntool ebuild
*Note: as of 04-03-2016 the fix was pushed upstream, so no need to overlay:* https://bugs.gentoo.org/show_bug.cgi?id=575380

`app-crypt/sbsigntool-0.6.r1` from this overlay differs from upstream `app-crypt/sbsigntool-0.6.r1` by depending on `binutils-libs`. Header file `bfd.h` was required in the compile phase, originally provided by `binutils` now moved to `bunutils-libs`. Log:

```
checking bfd.h usability... no
checking bfd.h presence... no
checking for bfd.h... no
configure: error: bfd.h not found.
bfd.h is usually distributed in a binutils development package.

```

