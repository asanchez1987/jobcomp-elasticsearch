## Installation

    # Change directory to your SLURM source directory
    cd slurm-14.11.3/
    wget -O jobcomp_es-0.3.tar.gz https://github.com/asanchez1987/jobcomp-elasticsearch/archive/v0.3.tar.gz
    tar xf ./jobcomp_es-0.3.tar.gz --strip-components=1
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
    JobCompLoc=http://YOUR_ELASTICSEARCH_SERVER:9200

Make sure that the ElasticSearch server is reachable from the Slurm controller host.

All the jobs will be stored in the **slurm** index with type **jobcomp**
