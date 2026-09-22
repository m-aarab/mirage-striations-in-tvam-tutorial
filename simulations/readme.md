
# Executing Mirage TVAM process simulations 

## Installation (one-time)
Make sure your system matches the requirements listed on [PyPI](https://pypi.org/project/mirage-optics-engine/).

Make sure the submodule repositories (`mirageVPP`, `DMDprojector-raydiscretizer`, `ModularHexMesh`) are also cloned:
```bash
git submodule update --init --recursive
```

Install required python modules, run from this directory:
```bash
python3 -m pip install -r ../mirageVPP/requirements.txt
```

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

4. Run the Mirage TVAM simulation. It should take about 45 minutes on an RTX A1000 or 5 minutes on an H100.

```bash
python3 ../../mirageVPP/mirage_TVAM.py --config *.sim.toml
```

5. Inspect results in ParaView (`results/cone_lincure.pvd`):

```bash
paraview results/*.pvd
```

$^*$ _note that the degree of cure in the simulation is normalized DoC_ $(\mathcal{\bar{X}})$. _True DoC_  $(\mathcal{{X}})$ _can found using the relation_ $\mathcal{\bar{X}}=\mathcal{{X}}/\mathcal{{X}_\text{max}}$ 
