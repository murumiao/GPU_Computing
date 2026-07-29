# How to build
Run ```make all```

# How to download matrixes
Run ```./scripts/download_matrixes.sh```. This script will download into ```./data``` 10 matrixes from SuiteSparse and sort them.

If you have matrixes and they are not sorted, please run ```./scripts/sort_matrixes.sh```

# How to run
By default, the binaries are located in the folder `./bin` 
```
mpiexec -n $NUMBER_PROCESSES <path_to_script> <path_to_matrix> 0 <n_threads_per_block> <shared_mem_size> [--lb <0|1|2>] [--save <path>]
```
