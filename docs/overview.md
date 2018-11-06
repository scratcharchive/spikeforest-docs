## SpikeForest server-side overview

### Q & A

[What is SpikeForest?](#what)

[Who is developing SpikeForest?](#who)

[Why is SpikeForest sprawled across so many repositories?](#why-sprawled)

[What are the core repositories/projects that SpikeForest depends on?](#core-projects)

[How are these documents compiled into the webpage at https://users.flatironinstitute.org/~magland/docs/?](#how-docs-compiled)

### What is SpikeForest? <a name="what"></a>

SpikeForest is a website and open source computing framework for evaluating and comparing spike sorting algorithms for neurophysiology data analysis. The system includes a collection of standard electrophysiology datasets together with ground truth information and a collection of spike sorting algorithms. Each algorithm is run against all datasets, and the results are updated on a daily basis as needed. You can browse all datasets, algorithms, sorting results, and comparisons, and inspect the source code used to generate these data.

### Who is developing SpikeForest <a name="who"></a>

SpikeForest is being developed at that Center for Computational Mathematics at the Flatiron Institute by Jeremy Magland, James Jun, Elizabeth Lovero, Alex Barnett, and Leslie Greengard. Our collaborators include ... TODO: list collaborators here...

### Why is SpikeForest sprawled across so many repositories? <a name="why-sprawled"></a>

Part of the answer is that this is Jeremy's programming style. But there are a lot of advantages of modularizing a project into small units that are individually tested and versioned. It also allows a lot of flexibility in how the components are mixed and matched, as there are a lot of different use cases for spike sorting and validation software. Modularity also allows multiple collaborators to operate in different domains without stepping on toes, and it permits the project to grow without the core becoming too bulky. The highest level scripts are simple github gists that are easily shared. Gists are not permitted to have subdirectories, and so it's not too intimidating to take a look at a gist source code. This is important for transparent, open, and reproducible science, because it's one thing to open your code, and another thing for it to be readable by other scientists.

Of course there are disadvantages of this approach. But those can ideally be mitigated by proper documentation in a centralized location. That is the purpose of this repository.

### What are the core repositories/projects that SpikeForest depend on? <a name="core-projects"></a>

SpikeForest depends on [KBucket](https://github.com/flatironinstitute/kbucket), [Pairio](https://github.com/magland/pairio), [SpikeInterface](https://github.com/colehurwitz31/spikeinterface), [SpikeWidgets](https://github.com/magland/spikewidgets), [SpikeToolkit](https://github.com/alejoe91/spiketoolkit), [MountainLab](https://github.com/flatironinstitute/mountainlab-js), [MLProcessors](https://github.com/flatironinstitute/mlprocessors), [SpikeForest server side](https://github.com/magland/spikeforest), [SpikeForest client side](https://github.com/elovero/spikeforest), and various gists.

### How are the docs compiled? <a name="how-docs-compiled"></a>

There is a checked-out version in Jeremy's home directory at Flatiron Institute. Every few minutes (in a tmux session), something like the following script is run:

```
cd ~/src/docs
git pull
mkdocs build
~www/sync
```

The actual script is found in ~/bin/wwwsync

Mkdocs is a python utility -- see [their website](https://www.mkdocs.org/) for more information. It operates on the mkdocs.yml at the root of this repository.



