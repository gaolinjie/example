The Three20 Modularized Build System
====================================

First, some history.

Three20 was originally built by Joe Hewitt as part of the Facebook for iPhone app. Since
then, the library has gone on to be used by countless developers in their efforts to
create amazing apps for the App Store. The Three20 community itself has blossomed to
include more than 800 developers in the Google Group and more than 2000 watchers on GitHub.

The library originally debuted with a number of powerful features, including the style system,
rethought table controllers and data sources, and a navigator with persistence. As time
progressed, more features were added to the library, and Three20 continued to prove to be a
versatile tool in many iPhone developers' arsenals on the App Store battlefield. Debug
utilities, JSON and XML support, and a growing set of sample applications and tutorials
were introduced over time.

But as Three20 grew, it began to experience growing pains. Many developers derided the
lack of documentation and comprehensive unit tests. More pointed out that some of the new
features being included in the Three20 library weren't critical for their needs, or
that they were already including some components, such as JSON parsers, in their own
projects. And some argued that if outside libraries were going to be included in Three20,
then the developer should still have a choice as to which library they actually want to use.

All of these requests were incredibly hard to satisfy given the way the Three20 library was
originally designed: **as a single library**.

### The Conceptual Split

In late 2009, when Jeff took over Three20, he spent a fair amount of time absorbing the
framework. He determined that there were four primary aspects to Three20: Core, Network,
Style, and UI. Each was dependent upon the previous aspect in the list, and collectively they
formed the Three20 library. Over the next five months a great deal of time was invested in
drawing lines in the sand in order to create a conceptual divide between the four aspects.  
  
  
  
  
  

Modular Three20
---------------

Three20 is now split into a set of libraries that, brought together, compose the original
Three20 library. The libraries are listed below for your information (kept up-to-date in the
DependencyCharts.mdown article):

    ------------------------------------------
    |                    UI                  |
    ------------------------------------------
    | UINavigator  |            |   Style    |
    |--------------|            |------------|
    |   UICommon   |            |  Network   |
    ------------------------------------------
    |                   Core                 |
    ------------------------------------------

And then there are the extensions.

    -------------   ------------
    |  extJSON  |   |  extXML  |
    -------------   ------------
    ----------------------------
    |          Network         |
    ----------------------------
    |           Core           |
    ----------------------------

If the diagrams aren't particularly clear to you, they're drawn as though the libs
were structured like a building; the lowest levels are the foundation and
the upper levels depend on the lower levels for support. Each "box" in the diagram
is a library.


What's Changed
--------------

A lot has changed in order to make Three20 a modular library. Many changes will
undoubtedly spur debate, but from a high perspective this new modular project structure
is going to be the way Three20 progresses into the future.


### Source Code Layout

**Who does this impact?** Anyone who has modified or wishes to modify the internals
of Three20.

#### The Old

    samples/               <- All sample code
    src/Three20/           <- All header files for Three20
    src/                   <- All implementation files for Three20
    src/Three20.bundle     <- The Three20 bundle
    src/Three20.xcodeproj  <- The project for the Three20 library

#### The New

    Articles/              <- Articles, such as this one, discussing Three20
    Build/                 <- All build output, including Products
    Build/Products/        <- The products of all libs and samples
    samples/               <- All sample code
    src/                   <- All project directories (see below)
    src/common/            <- Common files used by most libs
    src/scripts/           <- Common scripts used by most libs
    
    src/Three20.bundle     <- The Three20 bundle
    src/Three20.xcodeproj  <- The Legacy project for the Three20 library

A project directory looks as follows:

    Three20UI/Configurations/     <- Project-specific configurations
    Three20UI/Headers/            <- The lib's headers
    Three20UI/Sources/            <- The lib's implementation files
    Three20UI/Three20UI.xcodeproj <- The lib project
    Three20UI/UnitTests/          <- The lib's unit tests and related resources

#### Rationale behind the new project structure.

The biggest change of note is the movement of all source files to their specific
library's sub-directories. The reasoning for this is that, by separating the code
at some high level, it will be much easier to pull out a component of Three20 and
use it by itself.

Another notable change is the unification of the build output into a single
directory. This was done because of the way that headers are now handled;
all headers are copied into the `Build/Products/three20/` directory. Go check it out right now
if you've already built any of the new libs. This makes it possible to define the
noted directory as the "header search path" for all libraries instead of adding
each project's `Headers` directory to the header search path.

A nice side effect of having a unified build directory is that it makes it possible
to delete all build output by deleting a single directory. When hacking on
Three20 it can often be necessary to start from a clean slate in order to ensure
that the library isn't being built with phantom files.

