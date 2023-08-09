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

### Adding projects to test XNAT

```
(xnat4tests.venv) $ xnat4tests add-data simple-dir
(xnat4tests.venv) $ xnat4tests add-data openneuro-t1w
(xnat4tests.venv) $ xnat4tests add-data dummydicom
```


### Install Xnat4Tests in a virtualenv

Next we will install a package called `xnat4tests` that enables you to run your own
XNAT instance. It can be installed with

```
$ python3 -m venv ~/xnat4tests.venv
$ source ~/xnat4tests.venv/bin/activate
(xnat4tests.venv) $ pip install xnat4tests
(xnat4tests.venv) $ xnat4tests start
```


## Editing pipeline specifications

### Clone the community repository

```
$ git clone git@github.com:Australian-Imaging-Service/pipelines-community
```

### Install the depdencies in your virtual env

```
(xnat4tests.venv) $ cd ./pipelines-community
(xnat4tests.venv) $ pip install -r requirements.txt
```


### Building the specifications

To build the edited specifications, run the following command from your virtualenv from
the pipelines-community repository you cloned

```
(xnat4tests.venv) $ arcana deploy make-app ./australian-imaging-service-community xnat:XnatApp --loglevel info --build-dir ~/Desktop/pipelines-build-dir2 --use-test-config
```
