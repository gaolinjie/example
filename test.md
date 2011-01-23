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

