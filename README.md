
## snap packaging of R

### What is this?

This repo contains a [snapcraft](https://snapcraft.io) build recipe for the
[R](https://www.r-project.org) system for statistical computation and graphics.

### What is the current status?

It builds and runs but is still raw. Currently open issues are:

- locales are not provided by the core snap:
    - this is being worked as an core snap extension we plan to use once available
    - configuring with `--disable-nls` turns the support off yet the warnings persist
- packages cannot link though they now compile: possibly a path issue in `Makeconf`
    - this is not specific to R but to the `snap`, it also fails to compile and link simple C/C++ programs
    - run with `r-base.shell` to launch a shell and test there

### What is already done?

At the [June 2019 snapcraft summit](https://snapcraft.io/blog/2019/03/22/snapcraft-summit-montreal) a solid foundation was established:

- the [snapcraft](https://snapcraft.io) recipe builds R from source
- the resulting `snap` works in the preferred `strict` confiment
- several important system resources can be accessed and work:
   - networking is available and _e.g._ [CRAN packages](https://cran.r-project.org) can be downloaded
   - desktop resources (font metrics etc) are available, graphics work
   - all key R `capabilities()` are supported
- `Makeconf` reflects paths to headers and libraries reflecting the build stage,
however linking does not yet work but we are fairly close to compiling package
s### More documentation?

### More documentation?

Start at the [snapcraft](https://snapcraft.io) site itself with its link to the [docs](https://docs.snapcraft.io/) site.
