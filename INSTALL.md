## Installation

**IMPORTANT: Installation process will differ depending on your SLURM version**. So, for SLURM 15.08 onwards, plugin is already merged with SLURM and you should just check that **libcurl-devel** library is usable and configure the plugin.

On the other hand, if you want this plugin to be installed in SLURM versions PRIOR to 15.08, you should follow the following process:

    `cd' to the directory containing the SLURM package's source code and type
    $ wget -O jobcomp_es-0.7.tar.gz https://github.com/asanchez1987/jobcomp-elasticsearch/archive/v0.7.tar.gz
    $ tar xf ./jobcomp_es-0.7.tar.gz --strip-components=1
    $ ./autogen.sh
    $ ./configure
    # Ensure libcurl is usable:
    # ...
    # checking for curl-config... /usr/bin/curl-config
    # checking for the version of libcurl... 7.19.7
    # checking whether libcurl is usable... yes
    # checking for curl_free... yes
    # ...
    $ make
    $ make install
    
## Configuration

For any SLURM version the plugin can be enabled and configured through slurm.conf:

    JobCompType=jobcomp/elasticsearch
    JobCompLoc=http://YOUR_ELASTICSEARCH_SERVER:PORT
    
    Example:
    
    JobCompType=jobcomp/elasticsearch
    JobCompLoc=http://localhost:9200

Make sure that the ElasticSearch server is reachable from the SLURM controller host.

All the jobs will be stored in the **slurm** index with type **jobcomp**
