# Jupyter notebook

## Intro
Jupyter notebook is one the most widely used tools among data scientist. It allows you to try and present and share different ideas easily.
 Also I found it very useful to share codes for other data scientists and let them run the code.
 
## Setup the server
I usually start with creating a new environment

```bash
conda create -n py3 python=3

```

install `jupyter`:

```bash
conda install jupyter

```

create certification for secure communication:

```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout mykey.key -out mycert.pem

```

Generate `config` file:

```bash
jupyter notebook --generate-config
```
This will create a `config` file in the ~/.jupyter directory.
Edit the notebook config file, 'jupyter_notebook_config.py'. By default, the notebook config file has all fields commented out.

```python
c.NotebookApp.ip = '*'
c.NotebookApp.open_browser = False
c.NotebookApp.keyfile = u'/absolute/path/to/your/certificate/mykey.key' #if you want secure connection
c.NotebookApp.port = 9999 # It is a good idea to set a known, fixed port for server access

```

Create a passowrd for notebook

```bash
jupyter notebook password

```

It's a good idea to install `nb_conda`  and `nb_conda_kernels` if you want this environment be seen from other environments.

```bash
conda install nb_conda nb_conda_kernels

```

Now we are ready to launch the notebook:

```bash
jupyter notebook

```

Please note, if you are running the notebook on remote server through `ssh` as soon as you disconnect your connection, notebook will stop.
To avoid this problem, I usually use `screen` for running `notebook` and detach the screen after running. You can re-attach screen anytime you want. 