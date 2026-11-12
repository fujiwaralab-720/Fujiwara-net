# FujiwaraNet

This repository contains the simulation data of the thin-film materials used in the substrate-generalization evaluation (Fig. 3) of our study on deep learning ellipsometry with pseudo-substrate spectra. The data are provided solely to document the materials and thickness conditions used in that evaluation.

---

## Data Source

The optical constants of the thin-film materials were prepared with reference to the material database presented in

> H. Fujiwara and R. W. Collins (Eds.), *Spectroscopic Ellipsometry for Photovoltaics, Volume 2: Applications and Optical Data of Solar Cell Materials* (Springer, Cham, 2019).

Each material is represented by the dielectric-function model used in the database (Tauc–Lorentz, Sellmeier, or Tauc–Lorentz + harmonic oscillator), and the materials are grouped into folders according to the material categories of the database. The copyright of the original data belongs to the original reference.

---

## Directory Structure

```text
Fujiwaranet/
├── Organic(Tauc-Lorentz)/
├── Organic_Perovskites(Tauc-Lorentz)/
├── Semiconductor(Sellmeier)/
├── Semiconductor(Tauc-Lorentz)/
├── Semiconductor(Tauc-Lorentz+Harmonic Oscillator)/
├── Substrates-and-coating(Sellmeier)/
├── Substrates-and-coating(Tauc-Lorentz)/
├── TCO(Tauc-Lorentz)/
├── README.md
└── README-Japanese.md
```

The dielectric-function model of the materials in each folder is indicated in parentheses. Each folder contains one `*_nkd.csv` file per material, 123 files in total.

All 123 materials were used for the evaluations on the metal and SiO₂/Si substrates, whereas 107 materials were used for the evaluation on the transparent substrates, where the transparent thin-film materials were excluded.

---

## File Format: `*_nkd.csv`

| Column | Description |
|---|---|
| `Energy` | Photon energy (eV) |
| `n` | Refractive index |
| `k` | Extinction coefficient |
| `e1` | Real part of the dielectric function |
| `e2` | Imaginary part of the dielectric function |
| `ds_1`, `db_1`, …, `ds_6`, `db_6` | Six combinations of the surface-roughness layer thickness $d_s$ and bulk layer thickness $d_b$ (nm) used in the evaluation |

The optical constants are given row by row at each photon energy in the `Energy` column. The six thickness combinations are written only in the first data row. They were randomly selected for each material within the ranges $d_b$ = 10–300 nm and $d_s$ = 0–10 nm.
