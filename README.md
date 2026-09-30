![](/docs/images/graphabstr.svg)

# Numerical study of light self-focusing-induced striations in tomographic volumetric additive manufacturing
Marwan Aarab¹, Bo H. W. Moonen¹, Marc G. D. Geers¹, Joris J. C. Remmers¹

---

¹ Mechanics of Materials, Department of Mechanical Engineering, Eindhoven University of Technology

## Citation

If you use Mirage VPP in academic work, please provide attribution and cite the relevant paper(s).

Process simulation (placeholder untill published):

```bibtex
@article{aarab_numerical,
    title = "Numerical study of light self-focusing-induced striations in tomographic volumetric additive manufacturing",
    author = "Aarab, Marwan and Moonen, \{Bo H.W.\} and Geers, \{Marc G.D.\} and Remmers, \{Joris J.C.\}",
    year = "",
    doi = "",
    volume = "",
    pages = "",
    number = "",
    journal = "",
    publisher = "",
}
```

Physics engine:

```bibtex
@article{aarab_fast_2026,
    title = "Fast {Hessian}-free finite element ray tracing method for light transport in gradient-index media",
    author = "Marwan Aarab and Geers, \{Marc G.D.\} and Remmers, \{Joris J.C.\}",
    year = "2026",
    doi = "10.1364/OE.582633",
    volume = "34",
    pages = "10749--10769",
    journal = "Optics Express",
    publisher = "Optica Publishing Group",
    number = "6",
}
```

## Projection optimization
The projections were optimized using [TOMO](https://github.com/computed-axial-lithography/tomo). All files associated with this optimization, both inputs and outputs are presented in the folder `optimized_projections`.

## Simulations
> (!) Mirage VPP is currently a private repository, which will be released upon publication of `aarab_numerical`.

The configuration files for running the simulations are given in the `simulations` folder. Instructions on execution and installation are given in [this tutorial](/simulations/readme.md).

Note that the dimensions used in the simulations are:
- Time unit: $1$ s
- Length unit: $10$ μm
- Energy unit: $1$ nJ

From this we obtain derived units:
- Intensity unit: $1$ $\text{nW/(10 μm)}^2=1\ \mathrm{mW/cm}^2$
- Volumetric dosage or energy density unit: $1$ $\text{nJ/(10 μm)}^3=1\ \mathrm{J/cm}^3$


## License

The data and configuration files in this repository are licensed under [CC BY 4.0](/LICENSE.txt). However, the simulation code located in the `mirageVPP` directory is pulled from an external repository and is strictly licensed under [CC BY-NC 4.0]. You may not use the simulation code for commercial purposes.
