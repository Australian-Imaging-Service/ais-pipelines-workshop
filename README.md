# AIS Pipelines Workshop

## Getting setup

Unfortunately, these instructions will only work with MacOS and Linux systems. Windows
users will need to just follow along.

### Install Docker 

Please see the [official installation instructions for your system](https://docs.docker.com/get-docker/)

### Install Python3

If you haven't already, you will need to install Python with pip and virtualenv packages
on your system. There are many
ways to do this, which depend on your OS. A comprehensive guide can be found
[here](https://realpython.com/installing-python/).

In most casees, the above instructions will also install pip and virtual env, but if you
are on Linux you may also need to install the packages separately, e.g. `sudo apt install python3-pip`.


### Install Xnat4Tests in a virtualenv

Next we will install a package called `xnat4tests` that enables you to run your own
XNAT instance. It can be installed with

```
$ python3 -m venv ~/xnat4tests.venv
$ source ~/xnat4tests.venv
(xnat4tests.venv) $ pip install xnat4tests
(xnat4tests.venv) $ xnat4tests start
```


