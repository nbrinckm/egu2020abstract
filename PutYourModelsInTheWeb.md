Put your models in the web - less painful
=================================

Todays earth related scientific questions tend to be more complex and more interdisciplinary than ever before, so
it has become difficult for single persons or even institutions to tackle all aspects of them. We need to create composable and distributed frameworks to tackle these problems.

The technical solution for these frameworks lies in modern web technologies with a broad variety of standards, protocols. While restful services are one of the main drivers of the modern web, they are not suited for dealing
with scientific processes well. Restful services offer great flexibility, but they tend to be too specifc, too much bound to
very specific formats and they are often poorly documented.

In 2014 the Open Geospatial Consortium (OGC) published a standard to allow any kind of process / computation which doesn't have many of the
drawbacks of restful services: The Web Processing Service (WPS). The WPS interface allows to specify a set of input and output formats as well as
to explore the services with the GetCapabilities and DescribeProcess operations.

But there is one drawback: Since restful services are available for any programming language easily, WPS implementations
are currently mostly written in Java, C and Python.

In earth science we are confronted with a huge variety of programming languages and environments. It is simply not possible
to take all of the scientific programs and convert them into a language suitable for integration in WPS. Trying to do so often
results in conflicts and miss understanding between actual scientists and technical staff. This increases the
risk of introducing bugs in data / code conversion processes. Also the maintanance of these hybrid programs is often
very difficult since most scientists do not deal with web programming and technical staff does not know enough about the
actual science.

Tackled with these problems in the context of the RIESGOS project, we developed a framework for a Java based WPS Server 
to run any kind of scientifc scripts or command line programs regardless of the programming language by running the
actual code in docker.
Docker containers are used to encapsulate all dependencies of an executable independent of the host operating system.
How to call these executables is managed by configuration files: They specify how to call the executable, how to give input
parameters - e.g. command line arguments or input files - and how to read the output of the executable - from stdout, output
files, etc. We included several predefined ways on how to read and write a variety of formats and a mechanism to
extend them later.

The result is a encapsulated, composable, safe and extendable architecture that allows you as a scientist to put
your scientific executables right in the web with little to no effort. Once you can run your executable in docker, you
can run it on the web using a standardized service interface.
