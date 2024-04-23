# envs
Some notes of managing unique environment related issues

# Setting up kfp

Installing kfp (kubeflow pipelines)[https://www.kubeflow.org/].

The kfp package is installed via pip and we want to install it in a
conda environment.

kfp in mainly installed using the pip tool.

Starting the conda environmemnt and running pip install kfp, the
installation goes to the root python package. That is the python that
is outside of the conda environment. This means when pip is installed
in the conda environment, the import fails because pip installed the
package outside of the environment.

A solution is to use pip that is in the conda environment to install
the package. Pip should be install in the pip environment if pip it is
not installed

`conda install pip`

Using the conda version of pip to install the package will install the
package in the given environment.

`/home/ubuntu/miniconda3/envs/kfp/bin/pip install kfp`

Confirm that the package is installed in the right python's site packages

```(kfp) ubuntu@tfserver-gpu:~$ pip show kfp
Name: kfp
Version: 2.7.0
Summary: Kubeflow Pipelines SDK
Home-page: https://github.com/kubeflow/pipelines
Author: The Kubeflow Authors
Author-email: 
License: 
Location: /home/ubuntu/miniconda3/envs/kfp/lib/python3.12/site-packages

Requires: click, docstring-parser, google-api-core, google-auth,
google-cloud-storage, kfp-pipeline-spec, kfp-server-api, kubernetes,
protobuf, PyYAML, requests-toolbelt, tabulate, urllib3

Required-by:```
