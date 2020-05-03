<p align="center"> <img src="docs/img/modelci.png" alt="..."> </p>

# ML-Model-CI

[![Build Status](https://travis-ci.com/cap-ntu/ML-Model-CI.svg?token=SvqJmaGbqAbwcc7DNkD2&branch=master)](https://travis-ci.com/cap-ntu/ML-Model-CI)

## Features

- **Housekeeper** provides a refined management for model registration, deletion, update and selection.
- **Converter** is to convert models between frameworks.
- **Profiler** can diagnose a model and provide a detailed report about model performance in production environment.
- **Dispatcher** is to place models to devices and serve them automatically.
- **Controller** supports elastic test and deployment.

## Quick Start

### Installation

- [ ] One-step Docker installation [[Refer]](#intergration/README.md)

- [ ] step by step

<ol>

<li> Create environment

```shell script
# create environment
conda env create -f environment.yml

# install PyTorch with specific CUDA version
conda install pytorch torchvision cudatoolkit=<YOUR_CUDA_VERSION> -c pytorch
```

</li>

<li> Install MongoDB service

```shell script
docker run --rm -d -p 27017:27017 --name modelci-mongo mongo
```

And init database by:  
Go into the docker

```shell script
docker exec -ti modelci-mongo mongo
```

And create user:

```log
> use modelci
switch to db modelci
> db.createUser({user: "modelci", pwd: "modelci@2020", roles: ["readWrite"]});
Successfully added user: { "user" : "modelci", "roles" : [ "readWrite" ] }
> exit
bye
```

</li>

<li> Setup environment variables

Exporting environments
```shell script
set -o allexport
source modelci/env-mongodb.env
set +o allexport
```

If you are using an IDE to run the following test, remember to add `modelci/env-mongodb.env` as an EnvFile.

Exporting PYTHONPATH at the project root:
```shell script
export PYTHONPATH="${PATHONPATH}:${PWD}"
```
If you are using an IDE, set project root as source root.

</li>

</ol>

### Example

- [ ] a brief example (register, convert, dianose and deploy)

## Benchmark

- [ ] ModelZoo with model performance
