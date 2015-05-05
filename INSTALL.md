## Installation

This plugin is already merged in the SLURM master branch so just clone the master branch and use it.
Note that it will just work with SLURM versions 15.08.0pre1 onwards because in 15.08.0pre1 the structures with association in them were changed to assoc to save space.
    
    `cd' to the directory containing the package's source code and type
    ./autogen.sh
    ./configure
    # Ensure libcurl is usable:
    # ...
    # checking for curl-config... /usr/bin/curl-config
    # checking for the version of libcurl... 7.19.7
    # checking whether libcurl is usable... yes
    # checking for curl_free... yes
    # ...
    make
    make install


Plugin can be enabled and configured through slurm.conf, here is an example:

    JobCompType=jobcomp/elasticsearch
    JobCompLoc=http://YOUR_ELASTICSEARCH_SERVER:PORT
    
    Example:
    
    JobCompType=jobcomp/elasticsearch
    obCompLoc=http://localhost:9200

Make sure that the ElasticSearch server is reachable from the Slurm controller host.

All the jobs will be stored in the **slurm** index with type **jobcomp**
