
## snap packaging of R

### What?

This repo contains a [snapcraft](https://snapcraft.io) build recipes of
[R](https://www.r-project.org). 

### What is the Status

Still raw. A few open issues:

- locales are not provided by the core snap, this is being worked as a core snap extension
  we will use once available
- package cannot link though they now compile
  
### Done

At the [June 2019 snapcraft summit](https://snapcraft.io/blog/) a solid foundation was established:

- the recipe builds R from source (but is not yet as fully featured as _e.g._ the `deb` package)
- the resulting snap works in the preferred `strict` confiment
- several important system resources can be accessed:
   - networking is available and _e.g._ [CRAN packages](https://cran.r-project.org) can be downloaded
   - desktop resources (font metrics etc) are available
   - several key R `capabilities()` are already supported
- `Makeconf` reflect paths to headers and libraries reflecting the build stage, however linking
  does not yet work but we are fairly close to compiling package
