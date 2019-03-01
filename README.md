Dask CUDA
=========

Various utilities to improve interoperation between Dask and CUDA-enabled
systems.

This repository is designed to be a catch-all for Dask and CUDA utilities.
It is experimental and should not be relied upon.

Currently Includes
------------------

-   `LocalCUDACluster`: a subclass of `dask.distributed.LocalCluster` that
    eases deployment on single-node multi-GPU systems.


Example
-------

```python
from dask_cuda import LocalCUDACluster
from dask.distributed import Client

cluster = LocalCUDACluster()
client = Client(cluster)
```
## Setup from source

Setup from source repo:

1.  Install dependencies into a new conda environment
    ```bash
    conda create -n dask-cuda \
               -c conda-forge -c defaults \
                dask distributed
    ``` 
2. Activate conda environment:
    ```bash
    source activate dask-cuda
    ```
3.  Clone `dask_gdf` repo:
    ```bash
    git clone https://github.com/mrocklin/dask-cuda.git
    ```
4.  Install from source:
    ```bash
    cd dask-cuda
    pip install .
    ```
## Test

1.  Install `pytest`
    ```bash
    conda install pytest
    ```
2.  Run all tests:
    ```bash
    py.test dask_cuda
    ```
3. Or, run individual tests:
    ```bash
     py.test dask_cuda/tests/test_local_cuda_cluster.py
    ```