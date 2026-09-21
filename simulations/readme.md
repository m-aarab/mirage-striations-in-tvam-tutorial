
# Executing Mirage TVAM process simulations 

## Installation (one-time)
Install required python modules:
```bash
python3 -m pip install -r mirageVPP/requirements.txt
```

Make sure your system matches the requirements listed on [PyPI](https://pypi.org/project/mirage-optics-engine/).


## Running a simulation
All simulations have the same folder structure according to their `basename`:
```
num_basename
--frames (optional)
--basename.meshgen.toml
--basename.raygen.toml
--basename.sim.toml
```

The tutorial below will show how to execute the simulation in the folder `0_halfcone`, however all other folders will work identically.

1. Run from this directory:

```bash
cd 0_halfcone
```
### Generate mesh- and rayfiles (one-time)

2. Create the mesh:
```bash
python3 ../../mirageVPP/ModularHexMesh/cylindricalMesh.py --config *.meshgen.toml
```

3. Create the rays:
```bash
python3 ../../mirageVPP/DMDprojector-raydiscretizer/projectionImageGen.py --config *.raygen.toml
```

### Simulation execution

4. Run the Mirage TVAM simulation. It should take about 5 minutes (H100) depending on the GPU.

```bash
python3 ../../mirageVPP/mirage_TVAM.py --config *.vamsim.toml
```

5. Inspect results in ParaView (`results/cone_lincure.pvd`):

```bash
paraview results/*.pvd
```

$^*$ _note that the degree of cure in the simulation is normalized DoC ($\mathcal{\bar{X}}$). True DoC  ($\mathcal{{X}}$) can found using the relation_ $\mathcal{\bar{X}}=\mathcal{{X}}/\mathcal{{X}_\text{max}}$ 