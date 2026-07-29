# How to build
Run ```make all```

# How to download matrixes
Run ```./scripts/download_matrixes.sh```. This script will download into ```./data``` 10 matrixes from SuiteSparse and sort them.

If you have matrixes and they are not sorted, please run ```./scripts/sort_matrixes.sh```

# How to run
By default, the binaries are located in the folder `./bin` 
- for ```distributed_spmv.cu```
```
mpiexec -n <NUMBER_PROCESSES> <path_to_script> <path_to_matrix> 0 1024 0 [--save <path>]
```
- for ```distributed_spmv_2D.cu```
```
mpiexec -n <NUMBER_PROCESSES> <path_to_script> <path_to_matrix> 0 1024 0 [--lb <0|1|2>] [--save <path>]
```
- for ```distributed_spmv_NCCL.cu```
```
mpiexec -n <NUMBER_PROCESSES> <path_to_script> <path_to_matrix> 0 1024 0 [--lb <0|1|2>] [--save <path>]
```

where ```--lb <0|1|2>``` controls the load balancing mode:
- lb=0, uniform
- lb=1, balance on NNZ
- lb=2, balance on communication volume
