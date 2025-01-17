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


### Install and start Xnat4Tests in a virtualenv

Next we will install a package called `xnat4tests` that enables you to run your own
XNAT instance. It can be installed with

```
python3 -m venv ~/xnat4tests.venv
source ~/xnat4tests.venv/bin/activate
pip install xnat4tests
xnat4tests start
```

NB: It will take some time to build the Docker image, and then more time again to launch it, ~5 min in total

### Open up your browser to view test XNAT

Type `http://localhost:8080` into your browser and then login to XNAT using the username `admin` and password `admin`

### Adding sample-data to test XNAT

Xnat4Tests can also generate/download sample data to populate the test XNAT. There are currently 3 sample datasets, "simple-dir", "openneuro-t1w" and "dummydicom". They can be installed with

```
xnat4tests add-data simple-dir
xnat4tests add-data openneuro-t1w
xnat4tests add-data dummydicom
```


## Editing pipeline specifications

### Clone the community repository

```
git clone https://github.com/Australian-Imaging-Service/pipelines-community
```

### Install the pipelines-build depdendencies in a new virtual env

```
python3 -m venv ~/pipelines.venv
source ~/pipelines.venv/bin/activate
cd ./pipelines-community
pip install -r requirements.txt
```


### Building the specifications

To build the edited specifications, run the following command from your virtualenv from
the pipelines-community repository you cloned

```
arcana deploy make-app ./australian-imaging-service-community xnat:XnatApp --loglevel info --build-dir ~/pipelines-build-dir --use-test-config
```
