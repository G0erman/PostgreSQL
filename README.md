# PostgreSQL

[img[https://jupyter-docker-stacks.readthedocs.io/en/latest/_images/inherit.svg]]

We are going to use scipy-notebook image to play with PostgreSQL.

# Requiremets

- Docker

# Step by step

```bash
# Start container
$ docker run --name learn_postgresql -d -p 8881:8888 -e JUPYTER_ENABLE_LAB=yes -v $(pwd):/home/jovyan/work -t jupyter/scipy-notebook:latest

# Ingress to the container
$ docker exec -it learn_postgresql bash

# Start jupyter sever
$ jupyter server list
Currently running servers:
http://674ec66fd0e3:8888/?token=tokenn :: /home/jovyan

# Start jupyter lab in your browser
localhost:8881/?token=tokenn
```

# Installation try

```bash
(base) PostgreSQL$ docker exec -it -u root learn_postgresql bash
(base) root@7fff23409a00:~# !sudo apt list
sudo apt list apt list
Listing... Done
apt/now 2.0.5 amd64 [installed,local]
(base) root@7fff23409a00:~# jupyter list
Traceback (most recent call last):
  File "/opt/conda/bin/jupyter", line 11, in <module>
    sys.exit(main())
  File "/opt/conda/lib/python3.9/site-packages/jupyter_core/command.py", line 285, in main
    command = _jupyter_abspath(subcommand)
  File "/opt/conda/lib/python3.9/site-packages/jupyter_core/command.py", line 124, in _jupyter_abspath
    raise Exception(
Exception: Jupyter command `jupyter-list` not found.
(base) root@7fff23409a00:~# jupyter server list
Currently running servers:
http://7fff23409a00:8888/?token=b28e17402988613091e81c2b5bca97c74d7321d049592834 :: /home/jovyan
(base) root@7fff23409a00:~# apt-get install postgresql
Reading package lists... Done
Building dependency tree
Reading state information... Done
E: Unable to locate package postgresql
```

# To do:

- Install postgresql in another container.
- user docker compose.
- link the two projects.

