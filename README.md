# rethinkdb-jupyter-notebooks

These notebooks illustrate the use of
[RethinkDB: the open-source database for the realtime web](https://www.rethinkdb.com/) via
[Project Jupyter](http://jupyter.org/) notebooks.

For a demo, see
[Ryan Paul - Learn how to use RethinkDB with Jupyter - YouTube](https://www.youtube.com/watch?v=19K8buDmxjM)

A painless way to try these out, with minimal impact on your environment, is to follow these steps.

Install RethinkDB, e.g. via

    docker run -d -P --name rethink1 rethinkdb

Get the port on which RethinkDB is running, e.g. via

    export RETHINKDB_PORT_28015_TCP_PORT=`docker port rethink1 28015 | sed 's,.*:,,'`

Use [virtualenvwrapper](http://virtualenvwrapper.readthedocs.org/en/latest/index.html) to create a
very lightweight virtual environment with the lastest jupyter:

    mkvirtualenv rethinkdb
    pip install jupyter

Install the python dependencies and an ipython profile to define the `%r` command:
  to run RethinkDB inside jupyter

    jupyter notebook Configuration.ipynb
  
  or manually get the dependencies and create a `~/.ipython/profile_default/startup/rdb-extension.py` based on the steps at [Configuration.ipynb](https://github.com/segphault/rethinkdb-jupyter-notebooks/blob/master/Configuration.ipynb)

Run the Earthquake example:

    jupyter notebook Earthquake\ Example.ipynb
