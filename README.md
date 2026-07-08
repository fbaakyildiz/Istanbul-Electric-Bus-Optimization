# Istanbul Electric Bus Optimization

Senior design project repository for:

**Integrating Electric Buses to Istanbul Public Transportation System: Choosing the Right Routing and Number of Buses**

This project develops a simulation-based decision-support workflow for evaluating which Istanbul bus routes are suitable for electric bus deployment. The study focuses on the Historical Peninsula pilot region and compares electric bus alternatives against diesel bus operation under route, slope, passenger demand, traffic, and seasonal conditions.

## Project Summary

Istanbul's diesel bus fleet creates operational cost, emissions, and sustainability challenges. Electric buses reduce tailpipe emissions and noise, but deployment decisions are constrained by battery range, depot charging, passenger demand, road slope, route distance, and service frequency.

This project addresses the decision problem with a route-level discrete-event simulation built with SimPy. The model evaluates candidate routes using operational and environmental metrics, then ranks routes for staged electrification.

## Key Findings

- Pilot region: Historical Peninsula routes connected to Topkapi Garage and Eminonu-focused service patterns.
- Bus models compared: BYD K8, Karsan e-ATAK, and diesel Karsan ATAK baseline.
- Simulation method: discrete-event simulation with repeated replications and confidence interval analysis.
- Critical scenario: winter operation, due to higher HVAC-driven energy consumption.
- First-stage electrification candidates: `93`, `33`, `36KE`, `35`.
- Second-stage electrification candidates: `336E`, `38E`, `33B`.
- Preferred electric model in the study: BYD K8, because of lower average energy consumption, fewer depot visits, higher capacity, and lower CO2 emissions across most candidate routes.

## Repository Structure

```text
.
├── data/
│   └── README.md
├── docs/
│   └── DESIGN.md
├── notebooks/
│   ├── 01_route_distance_slope_extraction.ipynb
│   ├── 02_all_routes_discrete_event_simulation.ipynb
│   ├── 03_final_route_evaluation_analysis.ipynb
│   ├── 04_model_verification.ipynb
│   ├── 05_model_validation.ipynb
│   └── README.md
├── reports/
│   ├── final-report.pdf
│   └── README.md
├── .gitignore
├── README.md
└── requirements.txt
```

## Notebook Workflow

1. `01_route_distance_slope_extraction.ipynb` prepares route distance and slope inputs.
2. `02_all_routes_discrete_event_simulation.ipynb` contains the core SimPy model for candidate routes.
3. `03_final_route_evaluation_analysis.ipynb` analyzes battery, energy, passenger, and emissions results.
4. `04_model_verification.ipynb` checks model structure and simulation behavior.
5. `05_model_validation.ipynb` validates model behavior under passenger, slope, and no-passenger scenarios.

The notebooks were renamed and output-stripped for publication. Original class/project filenames, copies, and intermediate versions were intentionally excluded to keep the repository readable.

## Data Availability

The public repository does not include raw IETT operational datasets or API-derived route files. Some notebooks refer to local Excel inputs used during the senior design project. These data files should be placed under `data/raw/` when reproducing the analysis locally.

See [data/README.md](data/README.md) for the expected data categories.

## Documentation

- [Design document](docs/DESIGN.md)
- [Final report PDF](reports/final-report.pdf)

## Environment

Install dependencies:

```bash
pip install -r requirements.txt
```

Core dependencies:

- Python 3.10+
- SimPy
- pandas
- NumPy
- matplotlib
- seaborn
- scipy
- requests
- osmnx
- networkx
- openpyxl

## Academic Context

This repository represents a senior design project in Industrial Engineering. The model is intended as a decision-support prototype, not as a production scheduling system. Operational deployment would require refreshed IETT data, real-time traffic integration, charger availability modeling, and validation against live bus telemetry.
