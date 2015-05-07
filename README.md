## Introduciton

**jobcomp/elasticsearch** is a SLURM job completion plugin that inserts the information related
to finished jobs (COMPLETED, CANCELLED, FAILED, TIMEOUT or NODE_FAIL) in a custom
[ElasticSearch](http://www.elasticsearch.org/) server.

If data can't be indexed for whatever reason (server not reachable, index in readonly mode, etc.),
the plugin saves the job information in a state file for future retries.

It is a good idea to have a web layer over your ElasticSearch server, such as [Kibana](http://www.elasticsearch.org/overview/kibana/), in order to visualize the data.

Note that the plugin has **libcurl-devel** library as a dependency, so you can use these two
**configure** options:

    --with-libcurl (used by default, so not necessary)
    --without-libcurl

Here you can find some [Screenshots](https://github.com/asanchez1987/jobcomp-elasticsearch/wiki/Screenshots).

**NOTE:** Plugin is already merged in the SLURM 15.08 master branch. **If the plugin is needed to be installed in prior SLURM versions, you should install it separately**. Please, refer to  [INSTALL.md](https://github.com/asanchez1987/jobcomp-elasticsearch/blob/master/INSTALL.md) for installation instructions.

Any suggestions are more than welcome to asanchez1987@gmail.com / alejandro.sanchezgraells@bsc.es
