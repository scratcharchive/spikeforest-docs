## SpikeForest Overview

### Q & A

[What is SpikeForest?](#what)

[Who is developing SpikeForest?](#who)

[What are the core repositories/projects that SpikeForest depends on?](#core-projects)

[Why is SpikeForest spread across so many repositories?](#why-spread)

[Where are the SpikeForest datasets hosted?](#where-datasets-hosted)

[How can SpikeForest data and results be accessed from python?](#kbucket-access-python)

[How can SpikeForest data and results be accessed from JavaScript?](#kbucket-access-javascript)

[How are these documents compiled into the documentation webpage?](#how-docs-compiled)

### What is SpikeForest? <a name="what"></a>

SpikeForest is a website and open source computing framework for evaluating and comparing spike sorting algorithms for neurophysiology data analysis. The system includes a collection of standard electrophysiology datasets together with ground truth information and a collection of spike sorting algorithms. Each algorithm is run against all datasets, and the results are updated on a daily basis as needed. You can browse all datasets, algorithms, sorting results, and comparisons, and inspect the source code used to generate these data.

### Who is developing SpikeForest <a name="who"></a>

SpikeForest is being developed at that Center for Computational Mathematics at the Flatiron Institute by Jeremy Magland, James Jun, Elizabeth Lovero, Alex Barnett, and Leslie Greengard. Our collaborators include ... TODO: list collaborators here...

### What are the core repositories/projects that SpikeForest depend on? <a name="core-projects"></a>

SpikeForest depends on [KBucket](https://github.com/flatironinstitute/kbucket), [Pairio](https://github.com/magland/pairio), [SpikeInterface](https://github.com/colehurwitz31/spikeinterface), [SpikeWidgets](https://github.com/magland/spikewidgets), [SpikeToolkit](https://github.com/alejoe91/spiketoolkit), [MountainLab](https://github.com/flatironinstitute/mountainlab-js), [MLProcessors](https://github.com/flatironinstitute/mlprocessors), [SpikeForest server side](https://github.com/magland/spikeforest), [SpikeForest client side](https://github.com/elovero/spikeforest), and various gists.

### Why is SpikeForest spread across so many repositories? <a name="why-spread"></a>

Part of the answer is that this is Jeremy's programming style. But there are a lot of advantages of modularizing a project into small units that are individually tested and versioned. It also allows a lot of flexibility in how the components are mixed and matched, as there are a lot of different use cases for spike sorting and validation software. Modularity also allows multiple collaborators to operate in different domains without stepping on toes, and it permits the project to grow without the core becoming too bulky. The highest level scripts are simple github gists that are easily shared. Gists are not permitted to have subdirectories, and so it's not too intimidating to take a look at a gist source code. This is important for transparent, open, and reproducible science, because it's one thing to open your code, and another thing for it to be readable by other scientists.

Of course there are disadvantages of this approach. But those can ideally be mitigated by proper documentation in a centralized location. That is the purpose of this repository.

## Where are the SpikeForest datasets hosted? <a name="where-datasets-hosted"></a>

The datasets are hosted on KBucket shares, which are directories located on various computers. KBucket provides a simple way to host large files without needing to upload them to a central storage location. Files hosted on a KBucket share may be accessed from anywhere on the internet and are referenced by either kbucket:// or sha1:// URLs. Those URLs may be converted to http:// URLs and it is then possible to download portions of the hosted files. See the [KBucket project](https://github.com/flatironinstitute/kbucket) for more information.

At the time of writing this documentation, the SpikeForest datasets are located on the Flatiron Institute compute resources (ceph drive).

## What data format are KBucket datasets stored in?

(TODO)

## How can SpikeForest data and results be accessed from python? <a name="kbucket-access-python"></a>

All SpikeForest datasets and results are hosted on KBucket and may be retrieved using the KBucket python client (note: there is also a KBucket JavaScript client). For more details see the following [live notebook](https://colab.research.google.com/gist/magland/318c7bc43df9dd528f667589eaa2482d).

## How can SpikeForest data and results be accessed from JavaScript? <a name="kbucket-access-javascript"></a>

A live example of accessing SpikeForest results using the JavaScript/NodeJS KBucket client can be found in this [live example](https://w7pp32vo0w.codesandbox.io/).

## How are these docs compiled into the documentation webpage? <a name="how-docs-compiled"></a>

This documentation is [hosted on a webpage](https://users.flatironinstitute.org/~magland/docs/).

There is a checked-out version in Jeremy's home directory at Flatiron Institute. Every few minutes (in a tmux session), something like the following script is run:

```
cd ~/src/docs
git pull
mkdocs build
~www/sync
```

The actual script is found in ~/bin/wwwsync

Mkdocs is a python utility -- see [this website](https://www.mkdocs.org/) for more information. It operates on the mkdocs.yml at the root of [this repository](https://github.com/magland/docs).



