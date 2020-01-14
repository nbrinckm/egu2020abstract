Put your models in the web - less painful!
=================================

Today's Earth-related scientific questions are more complex and more interdisciplinary than ever, so much
that is extremely challenging for single-domain experts to master all different scientific aspects of the 
problem at once.
As a consequence, modular and distributed frameworks are increasingly gaining momentum, since they allow the
collaborative development of complex, multidisciplinary processing solutions.

An effective technical implementation focus on the use of modern web technologies with their broad variety of
standards, protocols and available development frameworks. RESTful services for instance are one of the main
drivers of the modern web, although they are often suboptimal for the implementation of complex scientific
processing solutions. In fact, while they offer great flexibility, they also tend to be bound to very
specific formats (and often poorly documented).

With the introduction of the Web Processing Service (WPS) specifications, the Open Geospatial Consortium (OGC)
proposed a standard for the implementation of a new generation of computing modules overcoming most of the
drawbacks of the RESTful approach. The WPS allow a flexible specification of input and output formats as well as
the exploration of the services´capabilities (e.g., with the GetCapabilities and DescribeProcess operations).

The main drawback of the WPS approach with respect to RESTful services is that the latter can be easily 
implemented for any programming language, while the efficient integration of WPS is currently mostly relying
on Java, C and Python implementations.

In the framework of Earth Science Research we are often confronted with a plethora of programming languages
and coding environments, including the use of mixed languages, and with unstructured (sometimes wild) 
programming practices. Converting already existing complex scientific programs into a language suitable for WPS 
integration can be a daunting effort and may even result in additional errors being introduced due to conflicts
and misunderstandings between the original code authors and the developers working on the WPS integration. 
Also the maintenance of these hybrid processing components is often very difficult since most scientists are not 
familiar with the technicalities of web programming and conversely the web developers cannot (or do not have the
time to) get adequately aquainted with the underlying scientific concepts.

Facing these problems in the context of the RIESGOS project we developed an innovative framework for a Java-based
WPS server able to run any kind of scientific code scripts or command line programs. The proposed approach is based
on the use of Docker containers encapsulating the running processes, and Docker images to manage all necessary dependencies.

A simple set of ASCII configuration files provides all metadata needed for WPS integration: how to call the program,
how to give input parameters - including command line arguments and input files - and how to interpret the output of
the program - both from  stdout and from serialized files. 
Predefined format converters can be easily integrated and later extended to ensure maximum compatilibility with
other WPSs.

The result is a encapsulated, modular, safe and extendable architecture that allows scientists to expose
their scientific programs on the web with little effort, and to collaboratively create complex, multidisciplinary
processing pipelines. 
