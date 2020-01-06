Put your models in the web: less painful
=================================

Todays Earth-related scientific questions are more complex and more interdisciplinary than ever before, so
much that is extremely challenging for single-domain experts to master all aspects of the problems. We need to go
more into modular and distributed frameworks in order to successfully tackle these problems.

A possible technical solution lies in the use of modern web technologies and their broad variety of standards, protocols and 
frameworks. RESTful services are one of the main drivers of the modern web, they are often suboptimal for the implementation of scientific processes. Whikle they offer great flexibility, they also tend to be too specifc, too much bounded to very specific formats (and often poorly documented).

With the introduction of the Web Processing Services (WPS) specifications, The OGC already in 2005 proposed a standard allowing the implementation of a new generation of computing modules overcoming most of the drawbacks of the RESTful approach. The WPS allows a flexible specification of input and output formats as well as
the exploration of the services´capabilities (with the GetCapabilities and DescribeProcess operations).

The only drawback of the WPS approach with respect to RESTful services is that the latter can be easily implemented for any programming language, while the integration of WPS is currently mostly relying on Java, C and Python implementations.

In the framwework of earth science research we are often confronted with a wide set of programming languages and coding environments, including the use of mixed languages, and unconstrained (sometimes wild) programming practices. Converting already existing complex scientific programs into a language suitable for WPS integration often is a daunting effort and may even results in new bugs being introduced due to conflicts and misunderstandings between the original authors and the developers attempting the integration. Also the maintanance of these hybrid processing components is often
very difficult since most scientists are not familiar with the technicalities of web programming and the web developers cannot (or do not have the time) get adequately aquainted with the underlying scientific concepts.

Facing the same problems in the context of the RIESGOS project we developed an innovative framework for a Java-based WPS Server able to run any kind of scientifc code scripts or command line program. The proposed approach is based on the use of Docker containers encapsulating the running process, and Docker images to manage all necessary dependencies.

How to call this programs is managed by configuration files: They specify how to call the program, how to give input
parameters - say command line arguments or input files - and how to read the output of the program - from stdout, output
files, etc. We included a bunch of predefined ways on how to read and write a variety of formats and a mechanism to
extend them later.

The result is a encapsulated, composable, safe and extendable architecture that allows you as a scientist to put
your scientific programs right in the web with little to no effort. Once you can run your script in docker, you
can run it on the web.
