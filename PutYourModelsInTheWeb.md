Put your models in the web - less painful
=================================

Todays earth related scientific questions are tend to be more complex and more interdisciplinary than ever before, so
that there is no change for single persons or even institutions to tackle all aspects of them any more. We need to go
more into composable and distributed frameworks to tackle these problems.

The technical solution for these is in modern web technologies with a broad variety of standards, protocols and 
frameworks. While restful services are one of the main drivers of the modern web, they are not suited for dealing
with scientific processes well. They offer great flexibility, but they tend to be too specific, too much bound to
very specific formats and they are often poorly documented.

However the OGC came by with a standard to allow any kind of process / computation which does not have many of the
drawbacks of restful services: Web processing service. The WPS allows to specify fix input and output formats as well as
to explore the services with the GetCapabilities and DescribeProcess operations.

But there is the drawback: Since restful services are available for any programming language easily, WPS integration
are currently mostly bound to Java, C and Python implementations.

In earth science we are confronted with a huge variety of programming languages and environments. It is simply not possible
to take all of the scientific programs and convert them into a language for WPS integration. Trying to do so often
results in conflicts and miss understanding between actual scientists and technical stuff. This may drives us to the
risk of introducing bugs in data / code conversion processes. Also the maintenance of these hybrid programs is often
very difficult since most scientists do not deal with web programming and technical stuff do not know enough about the
actual science.

Tackled with these problem in the context of the RIESGOS project, we developed a framework for a Java based WPS server 
to run any kind of scientific scripts or command line programs regardless of the scientific tool chain by running the
actual code in docker.
Docker containers are used to encapsulate the running process and docker images to manage dependencies of the program.
How to call this programs is managed by configuration files: They specify how to call the program, how to give input
parameters - say command line arguments or input files - and how to read the output of the program - from stdout, output
files, etc. We included a bunch of predefined ways on how to read and write a variety of formats and a mechanism to
extend them later.

The result is a encapsulated, composable, safe and extendable architecture that allows you as a scientist to put
your scientific programs right in the web with little to no effort. Once you can run your script in docker, you
can run it on the web.
