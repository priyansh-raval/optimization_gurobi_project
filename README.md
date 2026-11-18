# Optimization Gurobi Project

Python environment and notebook for the ORIE 5380 optimization project.

## Setup

Install [uv](https://docs.astral.sh/uv/getting-started/installation/), then run from the repository root:

```sh
uv sync --locked
source .venv/bin/activate
```

The project uses Python 3.14, selected by `.python-version`. Dependencies are pinned in `uv.lock`.

## Notebook

Open `src/ORIE5380_Project_Notebook.ipynb` in VS Code with the Python and Jupyter extensions. Select `.venv/bin/python` as the notebook kernel. Workspace settings run notebook cells from `src` so the existing `data/...` paths resolve correctly.

For another notebook editor, use `src` as the working directory. A kernel can be registered inside the environment with:

```sh
python -m ipykernel install --sys-prefix --name opt-project --display-name "Optimization Project (Python 3.14)"
```

The input CSV files are included in `src/data`. The assignment instructions are in `ORIE5380_Project.pdf`. The notebook contains model and plotting TODOs that must be completed before it can run end to end.

## Gurobi license

Installing `gurobipy` installs the Python solver interface, but the notebook's 10,000-variable license test requires a license that permits that model size. Configure your Gurobi academic or other suitable license before running it. Keep license files and credentials outside the repository.

## Reports

LaTeX sources and compiled PDFs are in `src/report`:

- `ORIE5380_Project_Report_1.tex`: completed Part 1 report.
- `ORIE5380_Project_Report_2.tex`: Part 2 boilerplate; replace all TODOs and figure placeholders before submission.

Compile from `src/report` so figure paths resolve:

```sh
cd src/report
pdflatex -interaction=nonstopmode -halt-on-error ORIE5380_Project_Report_1.tex
pdflatex -interaction=nonstopmode -halt-on-error ORIE5380_Project_Report_2.tex
```
