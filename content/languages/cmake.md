+++
title = "CMake"
description = ""
date = 2014-11-21T14:24:31Z
aliases = []
[extra]
id = 10464
[taxonomies]
categories = []
tags = []
+++

{{language
|exec=interpreted
|site=http://www.cmake.org/
|hopl=no
|tags=cmake}}
[[Category:Utility]]

CMake is a cross-platform make system, for compiling [[C]], [[C++]] or [[Fortran]] programs.
CMake uses a configuration file (CMakeLists.txt) to run configure tests,
find libraries, create targets, and generate a build system for
[[make|Unix make]] or another build tool.

This configuration file runs commands in CMake's own scripting language.

For Rosetta Code, most examples work with ''CMake 2.6'' or later
in ''process script mode'' (<code>cmake -P myscript.cmake</code>).

Many examples use features from 2.6, especially function().

In <code>cmake -P</code> mode, CMake runs the script but never creates a project.
So there are no configure tests and no targets.

==Simple project==
This example builds a small C program after checking if #include <sys/time.h> provides clock_gettime() or gettimeofday().


### CMakeLists.txt


```cmake
# CMakeLists.txt
cmake_minimum_required(VERSION 2.6)
project(simpletime C)  # This project will use the C compiler.

# Check if this system has clock_gettime() or gettimeofday(),
# then generate config.h with the results.
include(CheckSymbolExists)
check_symbol_exists(clock_gettime sys/time.h HAVE_CLOCK_GETTIME)
check_symbol_exists(gettimeofday sys/time.h HAVE_GETTIMEOFDAY)
configure_file(config.h.in config.h)

# Allow C to #include <config.h>, if doing out-of-source build.
include_directories(${CMAKE_CURRENT_BINARY_DIR})

# This target will make an executable from the given
# source files and any included header files.
add_executable(simpletime simpletime.c)

# The install target will install the executable
# to ${CMAKE_INSTALL_PREFIX}/bin.
install(TARGETS simpletime DESTINATION bin)
```



### config.h.in


```c
/* config.h, generated from config.h.in by CMake ${CMAKE_VERSION} */
#cmakedefine HAVE_CLOCK_GETTIME
#cmakedefine HAVE_GETTIMEOFDAY
```



### simpletime.c


```c
/* simpletime.c */
#include "config.h"

#if defined(HAVE_CLOCK_GETTIME) || defined(HAVE_GETTIMEOFDAY)
#include <sys/time.h>
#endif
#include <stdio.h>
#include <time.h>

/*
 * Simply print the current time.
 */
int
main()
{
#if defined(HAVE_CLOCK_GETTIME)
	struct timespec ts;
	clock_gettime(CLOCK_REALTIME, &ts);
	printf("The time is %s" "and %ld nanoseconds.\n",
	    ctime(&ts.tv_sec), ts.tv_nsec);
#elif defined(HAVE_GETTIMEOFDAY)
	struct timeval tv;
	gettimeofday(&tv, NULL);
	printf("The time is %s" "and %ld microseconds.\n",
	    ctime(&tv.tv_sec), tv.tv_usec);
#else
	time_t sec;
	sec = time(NULL);
	printf("The time is %s", ctime(&sec));
#endif
	return 0;
}
```


If the three files CMakeLists.txt, config.h.in and simpletime.c are in ..,
then <code>cmake ..</code> configures the project.

 $ cmake ..
 -- The C compiler identification is GNU
 -- Check for working C compiler: /usr/bin/gcc
 -- Check for working C compiler: /usr/bin/gcc -- works
 -- Detecting C compiler ABI info
 -- Detecting C compiler ABI info - done
 -- Looking for clock_gettime
 -- Looking for clock_gettime - found
 -- Looking for gettimeofday
 -- Looking for gettimeofday - found
 -- Configuring done
 -- Generating done
 -- Build files have been written to: /home/kernigh/field/rc/simpletime/work
 $ make
 <b style="color: magenta;">Scanning dependencies of target simpletime</b>
 [100%] <span style="color: green;">Building C object CMakeFiles/simpletime.dir/simpletime.c.o</span>
 <b style="color: red;">Linking C executable simpletime</b>
 [100%] Built target simpletime
 $ ./simpletime
 The time is Wed Sep  7 17:10:55 2011
 and 993848603 nanoseconds.
