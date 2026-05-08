# Algorithmic Bias in Recruitment
### by Trinity A. Royal & Donya Nicholson 
SCIS 432: Artificial Intelligence
## Project Purpose
This project automates an experiment to detect algorithmic bias in LLM-based recruitment tools. It generates resume pairs that are identical except for the university name, comparing Historically Black Colleges and Universities (HBCUs) against Predominantly White Institutions (PWIs). LLMs are used to score their suitability for a Software Engineering role and statistical analysis tests are performed using the LLM output.
## Functionality
### Synthetic Resume Generation 
Uses Faker and random seeding to create unique, balanced profiles.
### LLM Integration 
Supports DeepSeek (via Hugging Face/Novita) for resume evaluation.
### Statistical Analysis 
Automates Independent Samples T-Tests and Cohen’s d effect size calculations.
### Visualization
Generates box plots, violin plots, and per-pair difference charts.
## Installation
Ensure Python 3.10+ is installed, then run:
`pip install huggingface_hub pandas numpy scipy matplotlib seaborn faker` or `pip3 install huggingface_hub pandas numpy scipy matplotlib seaborn faker`
depending on version.
### Required Imports 
`import pandas as pd
import numpy as np
from scipy import stats
import matplotlib.pyplot as plt
import seaborn as sns
from huggingface_hub import InferenceClient`
## Authentication
### Hugging Face
Obtain a token from your HF settings. Use `notebook_login()` or pass the token to the `InferenceClient`
* This project utilizes the DeepSeek-V4-Flash model via the Novita provider on Hugging Face.
## Execution Guide
1. Configure API Keys: Set your HF_TOKEN in the configuration cell
2. Generate Resumes: Run the generation functions to create the 40+ unique resume pairs
3. Run Experiment: Execute the `run_experiment()` function. The pipeline includes rate-limiting (time.sleep) to avoid quota errors
4. Analyze: Run the statistical analysis cell to view T-test results and p-values
5. Visualize: Execute the plotting cells to generate comparative charts of the scores
## Statistical Analysis
The pipeline automatically performs an Independent Samples T-Test to evaluate the null hypothesis that there is no difference in scores between HBCU and PWI candidates. It also calculates Cohen's d to quantify the magnitude of any detected bias.
