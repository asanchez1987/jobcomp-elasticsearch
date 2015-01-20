1. Plugin uses libcurl-devel, so it has to be installed on the system.

2. New ./configure options have been added: --with-libcurl, --without-libcurl

3. Plugin can be enabled and configured through slurm.conf, here is an example:

    JobCompType=jobcomp/elasticsearch
    JobCompLoc=http://yourelasticserver:9200
  
4. Once data is inserted into elasticsearch, it is a good idea to visualize
it through a web layer such as Kibana:

    http://www.elasticsearch.org/overview/kibana/
    
5. Some screenshots have been placed inside screenshots/ directory

6. Any suggestions are welcomed to asanchez1987@gmail.com
