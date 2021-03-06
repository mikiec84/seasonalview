Graphical User Interface for Seasonal Adjustment
------------------------------------------------

An R package that unifies the 
[shiny](https://cran.r-project.org/package=shiny)-based graphical user 
interfaces from the [seasonal](https://cran.r-project.org/package=seasonal) and
[x13story](https://github.com/christophsax/x13story) packages and the online
adjustment tool on [www.seasonal.website](https://www.seasonal.website).

These interfaces have grown over time and have become difficult to maintain. The
**seasonalview** package is an attempt to unify their code base. It  takes the
best from each interface, and makes it available to the others. In a way, this
is a summary of what I learned about
[shiny](https://cran.r-project.org/package=shiny) and web development over the
last few years.

To install this early version of the package, use:

    devtools::install_github("christophsax/seasonalview")


### Seasonal

The main function of the package is the `view` function, which works exactly as
the current `inspect` function in
[seasonal](https://cran.r-project.org/package=seasonal). Here is an example:

    library(seasonalview)  # this will also load seasonal
    m <- seas(AirPassengers)
    view(m)

![seasonal](https://raw.githubusercontent.com/christophsax/seasonalview/master/img/seasonal.png)


### X-13 Story

If you have the [x13story](https://github.com/christophsax/x13story) package
installed, you can call the function with the `story` argument. This will render
an R Markdown document and produce a *story* on seasonal adjustment that can be
manipulated interactively. 

    view(story = system.file(package = "x13story", "stories", "x11.Rmd"))

![x13story](https://raw.githubusercontent.com/christophsax/seasonalview/master/img/x13story.png)


### Stand-alone

Finally, you can set up a stand-alone seasonal adjustment tool, either locally
or on a server. While itself not very useful, the `standalone` function
showcases how a local version of
[www.seasonal.website](www.seasonal.website) would look like:

    standalone()

![standalone](https://raw.githubusercontent.com/christophsax/seasonalview/master/img/standalone.png)


### License and Credits

**seasonalview** is free and open source, licensed under GPL-3. It is built on
top of a large number of fantastic open source tools. It uses
[shiny](https://cran.r-project.org/package=shiny) and
[shinydashboard](https://cran.r-project.org/package=shinydashboard), through
which it accesses [jQuery](https://jquery.com),
[bootstrap](http://getbootstrap.com) and
[AdminLTE](https://almsaeedstudio.com/themes/AdminLTE/index2.html), which in
turn depend on a plethora of open source web technologies themselves. It also
uses [dygraphs](http://dygraphs.com), and, of course,
[seasonal](https://cran.r-project.org/package=seasonal),
[x13binary](https://cran.r-project.org/package=x13binary) and
[X-13ARIMA.SEATS](https://www.census.gov/srd/www/x13as/), the wonderful seasonal
adjustment software by the U.S. Census Bureau.

Thanks for your feedback, your ideas and bug-reports. [Contact me.](mailto:christoph.sax@gmail.com)
