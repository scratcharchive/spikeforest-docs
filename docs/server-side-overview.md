## SpikeForest server-side overview

### Q & A

[How are these documents compiled into the webpage at https://users.flatironinstitute.org/~magland/docs/?](#how-are-the-docs-compiled)

### How are the docs compiled?

There is a checked-out version in Jeremy's home directory at Flatiron Institute. Every few minutes (in a tmux session), something like the following script is run:

```
cd ~/src/docs
git pull
mkdocs build
~www/sync
```

The actual script is found in ~/bin/wwwsync

Mkdocs is a python utility -- see [their website](https://www.mkdocs.org/) for more information. It operates on the mkdocs.yml at the root of this repository.



