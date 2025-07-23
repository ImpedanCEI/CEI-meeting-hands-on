# CAP-meeting-hands-on
Wakis introduction and hands-on examples prepared for the CAP section meeting: 
* https://indico.cern.ch/event/1558279/

Involving all our in-house python-packages of the impedance assessment workflow: 
* [`Wakis`](https://github.com/ImpedanCEI/wakis) for the 3D electromagnetic wakefield simulations,
* [`IDDEFIX`](https://github.com/ImpedanCEI/IDDEFIX) for partially decayed wake extrapolation,
* [`BIHC`](https://github.com/ImpedanCEI/BIHC) for impedance-induced beam power loss, and
* [`neffint`](https://github.com/ImpedanCEI/neffint) for impedance to wake function conversion for beam dynamics simulations.

## Getting started
You can install wakis from GitHub to have the latest changes into your conda environment:
```bash
pip install wakis['notebook']
pip install bihc neffint iddefix # optional satellite packages
```

### GPU setup

`wakis` uses `cupy` to access GPU acceleration with the supported NVIDIA GPUs (more info in [Cupy's website](https://cupy.dev/)).
Provided a compatible [NVIDIA CUDA GPU](https://developer.nvidia.com/cuda-gpus) or [AMD ROCm GPUs](https://www.amd.com/en/products/graphics/desktops/radeon.html) with the adequate drivers & Toolkit:

```
conda install -c conda-forge cupy cuda-version=11.8
```

### MPI setup
To run multi-CPU parallelized simulations, Wakis needs the following packages:

* OpenMPI installed in your operating system:
* Python package [`mpi4py`](https://mpi4py.readthedocs.io/en/stable/)
* Python package [`ipyparallel`](https://ipyparallel.readthedocs.io/en/latest/tutorial/intro.html) to start a MPI kernel inside notebooks

The preferred install method is through `conda-forge`:

```
conda install -c conda-forge mpi4py openmpi
```