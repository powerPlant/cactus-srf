Singularity recipe files for Cactus https://github.com/ComparativeGenomicsToolkit/cactus

### GPU and CPU versions
It seems the GPU version can toggle GPU usage, so we only need this version.

### generate symlinks
We want the executables matching `/^cactus/` to be exposed, as far as I can tell from the docs https://github.com/ComparativeGenomicsToolkit/cactus/blob/v2.4.4/README.md

This will create symlinks for those executables only, in this case for `cactus-2.4.4.sif`:
```
apptainer exec cactus-2.4.4.sif find /home/cactus/bin /home/cactus/cactus_env/bin -maxdepth 1 -executable -type f -name 'cactus*' -printf '%f\n' | xargs -L1 ln -s cactus-2.4.4.sif
```
