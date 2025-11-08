Accelerating Pandas

This project demonstrates how common Pandas operations can be transparently accelerated on the GPU using the **RAPIDS cuDF Pandas accelerator**.

It explores realistic large-scale data manipulation tasks (with ~1 million rows each) such as grouping, merging, value counting, and rolling-window smoothing — all executed through standard Pandas syntax, but running on GPU when cuDF is enabled.

---

Overview

The notebook includes five main sections:

| Block | Operation Type | Description |
|--------|----------------|--------------|
| **1** | `groupby()` | Aggregates simulated Iris flower data by species and color. |
| **2** | `merge()` | Performs an inner join between two large parking ticket datasets. |
| **3** | `groupby()` + `datetime` | Groups 1M parking violations by issue date and derives weekdays. |
| **4** | `value_counts()` | Finds the most common violation type per U.S. state. |
| **5** | `rolling().mean()` | Applies a 7-day rolling average to visualize daily violations per vehicle type. |

Each operation is designed to be *Pandas-compatible* and automatically benefits from GPU acceleration when run in a cuDF-enabled environment.

---

Setup & Requirements

You can run this project directly on **Google Colab** or on a **local RAPIDS environment**.

Option 1: Run on Colab (recommended)

1. Open the notebook in Google Colab.  
2. At the top, install RAPIDS cuDF:
   ```bash
   !pip install cudf-cu12 --extra-index-url=https://pypi.nvidia.com
   
Enable the cuDF Pandas accelerator inside the notebook:
%load_ext cudf.pandas

What the Code Demonstrates

Large-scale synthetic data generation
Creates 1M-row DataFrames with categorical, numeric, and date columns.

Transparent GPU acceleration
Shows that you can use normal Pandas syntax (pd.DataFrame, groupby, merge, etc.) with GPU execution by simply loading the cuDF extension.

Rich exploratory tasks
Simulates realistic analytics questions such as:

Which flower species and colors are most frequent?

Which parking violations are most common by state?

How do daily violations evolve over time (smoothed 7-day window)?

Visualization
Uses Matplotlib to plot rolling-mean trends over the last 100 days.


Repository Structure
pandas-gpu-acceleration/
│
├── pandas_gpu_demo.ipynb     
├── README.md                 
└── panda.png                   
