# Istanbul Electric Bus Optimization

[Back to Portfolio](https://fbaakyildiz.github.io/)

Simulation-based senior design project for evaluating electric bus deployment in Istanbul public transportation.

**Full project title:** Integrating Electric Buses to Istanbul Public Transportation System: Choosing the Right Routing and Number of Buses

## Project Materials

| Resource | Link |
|---|---|
| Final report | [Open PDF](reports/final-report.pdf) |
| Design document | [Open design document](docs/DESIGN.md) |
| Notebook workflow | [Open notebooks](notebooks/) |
| Data notes | [Open data notes](data/README.md) |
| GitHub repository | [fbaakyildiz/Istanbul-Electric-Bus-Optimization](https://github.com/fbaakyildiz/Istanbul-Electric-Bus-Optimization) |

## What The Project Does

- Evaluates candidate Istanbul bus routes for electric bus deployment.
- Focuses on Historical Peninsula routes connected to Topkapi Garage and Eminonu-oriented service patterns.
- Uses SimPy discrete-event simulation to model route operations, passenger demand, battery consumption, charging behavior, and emissions.
- Compares BYD K8 and Karsan e-ATAK electric buses against a diesel Karsan ATAK baseline.
- Tests summer and winter operating conditions, including HVAC-driven energy changes.
- Produces staged electrification recommendations based on feasibility and emissions reduction.

## Recommended Route Staging

### First Stage

Routes with stronger operational feasibility and high electrification potential:

- `93`
- `33`
- `36KE`
- `35`

### Second Stage

Promising routes that require closer operational review:

- `336E`
- `38E`
- `33B`

## Simulation Workflow

```text
Route, stop, schedule, and passenger data
    ↓
Distance and slope preparation
    ↓
Vehicle and season scenario setup
    ↓
SimPy discrete-event simulation
    ↓
Repeated replications and confidence intervals
    ↓
Battery, energy, passenger, and emissions analysis
    ↓
Route ranking and electrification recommendation
```

## Notebook Set

| Notebook | Purpose |
|---|---|
| `01_route_distance_slope_extraction.ipynb` | Prepares route distance and slope inputs |
| `02_all_routes_discrete_event_simulation.ipynb` | Runs the main SimPy simulation model |
| `03_final_route_evaluation_analysis.ipynb` | Analyzes route feasibility, energy, emissions, and passenger metrics |
| `04_model_verification.ipynb` | Checks model mechanics and internal consistency |
| `05_model_validation.ipynb` | Tests behavior under passenger, slope, and simplified route scenarios |

## Main Decision Criteria

- ability to complete scheduled service
- battery state of charge before depot return
- number of charging visits
- passenger fulfillment
- total energy consumption
- CO2 emissions compared with diesel baseline
- seasonal robustness, especially winter operation

## Key Finding

The study favors BYD K8 for the evaluated pilot routes because it generally provides stronger capacity, lower average energy consumption, fewer depot charging visits, and lower CO2 emissions across most scenarios.

## Reproducibility Note

The repository is structured for review and documentation. Raw IETT operational files and API-derived route inputs are not committed. To rerun the full workflow, place the required local data files under `data/raw/` and follow the notebook sequence.

## Academic Disclaimer

This is an academic senior design project and should be treated as a decision-support prototype. Production deployment would require updated IETT data, live traffic assumptions, charger-capacity modeling, procurement constraints, and stakeholder validation.
