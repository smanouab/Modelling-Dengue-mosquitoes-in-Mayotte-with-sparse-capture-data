# Modelling-Dengue-mosquitoes-in-Mayotte-with-sparse-capture-data
Modelling Dengue mosquitoes in Mayotte with sparse capture data.
# Modelling Dengue Mosquitoes in Mayotte with Sparse Capture Data

**Weather-driven mathematical modelling, sensitivity analysis, and Bayesian calibration of dengue mosquito populations in Mayotte.**

## Overview

This repository contains the computational framework associated with the research article:

**"Modelling weather-driven dynamics of dengue mosquitoes in Mayotte with sparse capture data"**

**Authors:**
- G. Hilário — Instituto de Matemática, Universidade Federal do Rio de Janeiro, Brazil
- S. Manou-Abi — Laboratoire de Mathématiques et Applications, Université de Poitiers, France
- J. Balicchi — Agence Régionale de Santé de Mayotte, France
- B. Ainseba — Institut de Mathématiques de Bordeaux, Université de Bordeaux, France
- S. Boatto — Instituto de Matemática, Universidade Federal do Rio de Janeiro, Brazil

The project develops a mathematical and computational framework to investigate the weather-driven dynamics of dengue mosquito populations in Mayotte, a French overseas department where dengue is endemic.

The main objective is to understand how climatic conditions, particularly temperature and rainfall, influence the abundance and seasonal dynamics of *Aedes albopictus* and *Aedes aegypti*.

The framework combines physiologically structured population models, differential equations, global sensitivity analysis, and Bayesian calibration using sparse mosquito capture data.

## Scientific Background

Dengue prevention relies heavily on controlling mosquito vectors. Understanding the relationship between environmental conditions and mosquito population dynamics is therefore essential for public health surveillance and intervention planning.

In Mayotte, mosquito capture data are often sparse and contain a substantial proportion of zero observations. This creates important challenges for conventional parameter estimation techniques, particularly least-squares and correlation-based approaches.

To address these challenges, this work proposes a mechanistic population model coupled with a statistical observation framework that explicitly accounts for unknown mosquito trap efficiencies.

## Mathematical Model

The mosquito life cycle is represented through a stage-structured population model involving:

- Dry eggs;
- Aquatic immature stages;
- Adult mosquitoes.

The aquatic stages are described using **McKendrick–von Foerster equations**, with physiological age as the structuring variable.

Ordinary differential equations describe dry eggs and adult populations.

The model incorporates environmental dependencies through:

- Temperature-dependent development and transition rates;
- Rainfall-dependent environmental effects;
- A water-availability index;
- Stage-dependent mortality rates;
- Density-dependent larval mortality.

The resulting system couples nonlinear partial differential equations and ordinary differential equations.

A mathematical well-posedness result establishes the existence and uniqueness of solutions under the assumptions developed in the article.

## Computational Methodology

The computational framework is organized around four main components.

### 1. Parameter Estimation from Laboratory Data

Development and transition rates for immature mosquito stages are estimated using laboratory life-table data.

These estimates provide biologically informed parameter values for the population model.

### 2. Global Sensitivity Analysis

A variance-based Sobol sensitivity analysis is performed to identify the parameters that have the greatest influence on population dynamics.

Smooth surrogate models are used to approximate the times of minimum and maximum mosquito abundance.

This analysis helps distinguish parameters that can be fixed from those that need to be estimated using field observations.

### 3. Statistical Observation Model

Adult mosquito capture counts are represented through an inhomogeneous Poisson process.

The observation model explicitly incorporates unknown trap efficiencies.

These nuisance parameters are integrated out analytically, leading to a marginal likelihood that accommodates sparse observations and excess zero counts.

This approach avoids the extinction-related fitting failures encountered with conventional least-squares and correlation-based calibration methods.

### 4. Bayesian Calibration

The remaining model parameters are calibrated using four years of adult mosquito capture data collected in Mayotte.

The calibrated model is then used to reproduce seasonal population patterns and generate spatial maps of predicted relative mosquito abundance across the island.

## Repository Structure

The repository is organized around the following computational components:

```text
Modelling-Dengue-mosquitoes-in-Mayotte-with-sparse-capture-data/
│
├── README.md
│
├── notebooks/
│   └── Main_analysis.ipynb
│
├── src/
│   ├── model.py
│   ├── environmental_forcing.py
│   ├── parameter_estimation.py
│   ├── sensitivity_analysis.py
│   ├── observation_model.py
│   └── bayesian_calibration.py
│
├── data/
│   ├── laboratory/
│   ├── weather/
│   └── mosquito_captures/
│
├── results/
│   ├── figures/
│   ├── sensitivity/
│   ├── calibration/
│   └── spatial_predictions/
│
└── requirements.txt
```

*Note: This is a suggested organizational structure. The directory and file names should be adjusted to match the actual repository contents.*

## Software and Dependencies

The computational implementation is based on Python.

The main scientific Python libraries used in this project include:

- **NumPy** — numerical computations;
- **SciPy** — numerical integration and scientific computing;
- **Pandas** — data processing and manipulation;
- **Matplotlib** and **Seaborn** — visualization;
- **SALib** — Sobol global sensitivity analysis;
- **Jupyter Notebook** — interactive computational analyses.

The complete list of dependencies should be provided in `requirements.txt`.

## Installation

Clone the repository:

```bash
git clone https://github.com/USERNAME/Modelling-Dengue-mosquitoes-in-Mayotte-with-sparse-capture-data.git

cd Modelling-Dengue-mosquitoes-in-Mayotte-with-sparse-capture-data
```

Create and activate a Python virtual environment:

```bash
python -m venv venv
```

On Linux and macOS:

```bash
source venv/bin/activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

## Reproducibility

The Python implementation is intended to provide a unified and reproducible computational environment for the numerical experiments presented in the article.

The accompanying notebook documents the main computational workflow, including:

1. Environmental data preprocessing;
2. Laboratory-based parameter estimation;
3. Numerical simulation of mosquito population dynamics;
4. Sobol sensitivity analysis;
5. Statistical modelling of mosquito capture counts;
6. Bayesian parameter calibration;
7. Seasonal dynamics visualization;
8. Spatial prediction of relative mosquito abundance.

The numerical results and figures presented in the manuscript should be reproducible using the corresponding data and computational scripts, subject to the availability of the original datasets and the specified computational settings.

## Data Availability

The analyses rely on laboratory life-table data, meteorological observations, and adult mosquito capture records from Mayotte.

Data availability and access conditions should be specified in accordance with the agreements governing the use of the original datasets, particularly those provided by the Agence Régionale de Santé de Mayotte.

Restricted or confidential surveillance data are not necessarily distributed with this repository.

## Applications and Perspectives

The proposed framework provides a mathematical and statistical tool for:

- Understanding weather-driven mosquito population dynamics;
- Investigating the effects of rainfall and temperature on vector abundance;
- Identifying the most influential biological and environmental parameters;
- Calibrating mechanistic models with sparse ecological observations;
- Producing spatial predictions of relative mosquito abundance;
- Supporting epidemiological surveillance and vector-control strategies in Mayotte.

More generally, the methodology can be adapted to other vector-borne disease systems and geographical settings where environmental forcing and sparse capture data are important modelling challenges.

## Citation

If you use this repository in your research, please cite the associated scientific article:

```bibtex
@article{hilario_manouabi_dengue_mayotte,
  title   = {Modelling weather-driven dynamics of dengue mosquitoes
             in Mayotte with sparse capture data},
  author  = {Hil{\'a}rio, G. and Manou-Abi, S. and Balicchi, J.
             and Ainseba, B. and Boatto, S.},
  journal = {Preprint},
  year    = {2026}
}
```

The final bibliographic information will be updated once the article is published.

## Acknowledgements

The authors acknowledge the scientific and institutional collaborations that contributed to this research, particularly the ARS contributions associated with mosquito surveillance and environmental data collection in Mayotte.

## License

The licensing terms for the source code and data will be specified separately. Please contact the authors before redistributing restricted datasets or using them for purposes outside the scope of the original agreements.

---

**Correspondence:** S. Manou-Abi  
Laboratoire de Mathématiques et Applications  
Université de Poitiers, France
