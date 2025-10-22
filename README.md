# Data Processing & GitHub Pages Deployment Project

This project sets up an automated pipeline to process data using Python and Pandas, lint the code with Ruff, and publish the results to GitHub Pages using GitHub Actions.

## Project Structure

```
.
├── .github/workflows/
│   └── ci.yml
├── execute.py
├── data.xlsx  (Input file, manually converted to data.csv)
├── data.csv   (Generated from data.xlsx, used by execute.py)
├── index.html (Project landing page)
└── README.md
└── LICENSE
```

## Setup and Local Development

### Prerequisites

Ensure you have Python 3.11+ installed. We recommend using a virtual environment.

```bash
python -m venv .venv
source .venv/bin/activate # On Windows: .venv\Scripts\activate
```

### 1. Convert `data.xlsx` to `data.csv`

The `execute.py` script expects `data.csv` as its input. You need to convert your `data.xlsx` file to `data.csv` manually. A simple way to do this using Pandas is:

```python
import pandas as pd

df = pd.read_excel('data.xlsx')
df.to_csv('data.csv', index=False)
```

Save this script (e.g., `convert.py`), place `data.xlsx` in the project root, and run `python convert.py`. Ensure `data.csv` is created in the project root.

### 2. Install Dependencies

Install the required Python packages:

```bash
pip install pandas==2.3 ruff
```

### 3. `execute.py` (Fixed Version)

Below is the corrected `execute.py` script. The original script might have had a 