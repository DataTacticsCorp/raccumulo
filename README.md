Package: raccumulo  
Type: Package  
Title: R and Accumulo Connector  
Version: 1.0  
Date: 2013-05-09  
Author: Data Tactics Corporation  
Depends: R (>= 2.6.0), methods  
Maintainer: Data Tactics Corporation <pgrim@data-tactics.com>  
Description: Functions to create and delete Accumulo tables and read/write/scan rows from Accumulo tables  
License: Apache License (== 2.0)  
Packaged: 2013-05-09 22:18:20 UTC; pgrim  

INSTALLATION

1. Environment

raccumulo was developed and tested using Apache Accumulo 1.5.0 and Thrift 0.9.0.  
Building and installing raccumulo has only been tested on Linux platforms (CentOS 6.x
and Ubuntu 13.10).

2. Prerequisites

raccumulo is a source package.  Installation requires compiling of C source code.

raccumulo depends on Apache Thrift to communicate with the Accumulo Thrift proxy.
Before attempting to install raccumulo, please ensure that Thrift is installed.
More information on installing Thrift can be found at http://thrift.apache.org

To use raccumulo, an Accumulo proxy must be configured and running on the target
cluster.  See $ACCUMULO_HOME/proxy/proxy.properties for the configuration options.
The proxy is started using 
  
  $ACCUMULO_HOME/bin/accumulo proxy -p $ACCUMULO_HOME/proxy/proxy.properties

3. Installing

raccumulo can be acquired from GitHub using the following command:

  git clone https://github.com/DataTacticsCorp/raccumulo.git

Once the code is acquired, it can be installed by changing directory into
the raccumulo directory and executing the following command:

  R CMD INSTALL package

which will cause R to configure, compile, and install the raccumulo package.

The most common problems with installation are improperly configured PKG_CONFIG_PATH
and LD_LIBRARY_PATH.  PKG_CONFIG_PATH must include the directory where thrift.pc 
exists (/usr/local/lib/pkgconfig by default) and LD_LIBRARY_PATH must include the 
path to the Thrift shared libraries (/usr/local/lib by default) or /etc/ld.so.conf 
must be properly configured.

4. Usage

Once raccumulo is installed, it can be used from with R by loading the library as with
any other R package:

  library(raccumulo)

Examples of initializing and using raccumulo can be found in raccumulo/package/noinst/test.R.
Manual pages can be found in the R shell by using

  ?raccumulo
