## 📢 News & Media
**[Feb 2026] Official Press Release:** [Global AI ROI Study: 200 Case Analysis Reveals 159.8% Median Gains](./PRESS-RELEASE.md)

# AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17795133.svg)](https://doi.org/10.5281/zenodo.17795133)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)

## Overview

This repository contains an empirical dataset analyzing 200 artificial intelligence (AI) deployments in French B2B companies from 2022 to 2025. It provides quantitative evidence of AI return on investment (ROI), deployment durations, cost structures, and failure patterns across multiple sectors and company sizes.

**Author:** Denis ATLAN  
**Organization:** ENDKOO / HumaLoop  
**Date:** December 2025  
**Version:** 1.0

## Key Findings

- **Success Rate:** 82.5% (vs. 5-20% market benchmark)
- **Median ROI:** 159.8% over 24-month horizon
- **Top Performing Sectors:** Retail (242%), Finance (187%), Manufacturing (171%)
- **Human-in-the-Loop Adoption:** 88.5% of successful projects
- **Deployment Speed:** 94 days (SME) to 387 days (Large enterprises)

## Repository Structure

```
ai-roi-dataset/
├── data/
│   ├── ai_roi_dataset_200_deployments.csv    # Main dataset (200 projects)
│   └── data_dictionary.md                     # Variable definitions
├── notebooks/
│   └── ai_roi_analysis.ipynb                  # Reproducible analysis
├── docs/
│   ├── technical_report_ai_roi.md             # Full technical report
│   └── methodology.md                         # Detailed methodology
├── figures/
│   └── [Generated charts from notebook]
├── README.md                                  # This file
├── LICENSE                                    # CC BY 4.0
├── CITATION.cff                               # Citation metadata
├── requirements.txt                           # Python dependencies
└── CHANGELOG.md                               # Version history
```

## Dataset Description

### Variables (20 columns, 200 rows)

#### Project Identifiers
- `project_id`: Unique anonymized identifier (P001-P200)
- `year`, `quarter`: Temporal markers (2022-2025)

#### Company Characteristics
- `sector`: Industry vertical (10 categories)
- `company_size`: SME (10-49), ETI (50-249), Large (250+)
- `revenue_m_eur`: Annual revenue in millions of euros

#### AI Deployment Characteristics
- `ai_use_case`: Primary business objective (8 categories)
- `deployment_type`: Technical category (Automation, NLP, Analytics, Vision, Hybrid)
- `human_in_loop`: Binary (0=Fully automated, 1=HITL governance)

#### Timeline Metrics
- `days_diagnostic`: Duration of initial assessment phase
- `days_poc`: Proof-of-concept development duration
- `days_to_deployment`: Total time from kickoff to production
- `days_to_positive_roi`: Time until cumulative gains exceed investment

#### Financial Metrics
- `investment_eur`: Total investment (CAPEX + Year 1 OPEX)
- `annual_gain_eur`: Measured annual economic gain
- `roi_percent`: Calculated ROI over 24-month horizon

#### Outcome Metrics
- `failure`: Binary (0=Success, 1=Failure)
- `failure_reason`: Root cause (if failure)
- `time_saved_hours_month`: Productivity gain in hours per month
- `revenue_increase_percent`: Revenue uplift (if applicable)

## Getting Started

### Prerequisites

```bash
Python 3.9+
pip install -r requirements.txt
```

### Quick Start

```bash
# Clone the repository
git clone https://github.com/denisatlan/ai-roi-dataset.git
cd ai-roi-dataset

# Install dependencies
pip install -r requirements.txt

# Run the analysis notebook
jupyter notebook notebooks/ai_roi_analysis.ipynb
```

### Reproduce Key Statistics

```python
import pandas as pd

# Load dataset
df = pd.read_csv('data/ai_roi_dataset_200_deployments.csv')

# Success rate
success_rate = 1 - df['failure'].mean()
print(f"Success Rate: {success_rate:.1%}")  # 82.5%

# Median ROI (successful projects)
df_success = df[df['failure'] == 0]
median_roi = df_success['roi_percent'].median()
print(f"Median ROI: {median_roi:.1f}%")  # 159.8%

# Human-in-the-Loop adoption
hitl_rate = df['human_in_loop'].mean()
print(f"HITL Adoption: {hitl_rate:.1%}")  # 88.5%
```

## Key Visualizations

The Jupyter notebook generates 6 key visualizations:

1. **Distribution by Sector & Company Size** (`distribution_sectors_size.png`)
2. **ROI by Sector (Boxplot)** (`roi_by_sector_boxplot.png`)
3. **Investment & Gains by Company Size** (`investment_gains_by_size.png`)
4. **Deployment Durations by Phase** (`durations_by_size.png`)
5. **Failure Reasons Distribution** (`failure_reasons.png`)
6. **Human-in-the-Loop Impact** (`hitl_impact.png`)

## Methodology

### Data Collection
- **Sources:** Direct client projects (82.5%), advisory engagements (14%), partner case studies (3.5%)
- **Period:** January 2022 - December 2025
- **Inclusion criteria:** B2B enterprise (≥10 employees), production deployment or explicit termination, 6+ month tracking

### ROI Calculation
```
ROI (%) = [(Annual Gain × 2) - Investment] / Investment × 100
```
- 24-month horizon
- Conservative approach (does not account for Years 3+ value)

### Ethical Considerations
- All client data anonymized
- Revenue figures rounded
- No personally identifiable information (PII)

## Limitations & Biases

1. **Selection Bias:** Dataset reflects successful deployment methodology; market-wide failure rates are higher (80-95%)
2. **Geographic Limitation:** French market focus (Lyon/Auvergne-Rhône-Alpes)
3. **Temporal Heterogeneity:** 2022-2025 period spans rapid GenAI evolution
4. **ROI Measurement:** 24-month horizon may underestimate long-term value

See [Technical Report](docs/technical_report_ai_roi.md) Section 11 for full discussion.

## Citation

If you use this dataset in your research or work, please cite:

```bibtex
@techreport{atlan2025ai,
  title={AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025)},
  author={Atlan, Denis},
  year={2025},
  institution={ENDKOO / HumaLoop},
  type={Technical Report},
  url={https://github.com/denisatlan/ai-roi-dataset},
  doi={10.5281/zenodo.17795133}
}
```

**APA Format:**
```
Atlan, D. (2025). AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025). 
ENDKOO / HumaLoop. https://doi.org/10.5281/zenodo.17795133
```

## License

This dataset is licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You are free to:
- **Share** — copy and redistribute the material
- **Adapt** — remix, transform, and build upon the material

Under the following terms:
- **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made

## Publications & Media

- [Technical Report (PDF)](docs/technical_report_ai_roi.md)
- [Zenodo Repository](https://doi.org/10.5281/zenodo.17795133)
- [Kaggle Dataset](https://www.kaggle.com/datasets/denisatlan/ai-roi-200-b2b-deployments)
- [Personal Website: Research Section](https://denisatlan.fr/research)

## Related Work

- Atlan, D. (2025). *Human-in-the-Loop AI Governance Framework*. ENDKOO.
- Atlan, D. (2024). *AI Deployment Playbook for SMEs*. HumaLoop.

## Contact

**Denis ATLAN**  
Founder & Fractional CAIO  
ENDKOO / HumaLoop

- **ORCID:** [0009-0007-0785-7305](https://orcid.org/0009-0007-0785-7305)
- **Google Scholar:** [Profile](https://scholar.google.com/citations?user=LKa9rV8AAAAJ)
- **Email:** denis@denisatlan.fr
- **LinkedIn:** [linkedin.com/in/denisatlan](https://linkedin.com/in/denisatlan)
- **Website:** [denisatlan.fr](https://denisatlan.fr)
- **Conference Speaker:** [conferencier.ai](https://conferencier.ai)

## Acknowledgments

This research was conducted with the support of:
- 165 client companies (anonymized)
- Task Force 20 expert network
- Regional digital transformation initiatives (Auvergne-Rhône-Alpes)

## Changelog

### Version 1.0 (December 2025)
- Initial public release
- 200 projects analyzed (2022-2025)
- 20 variables documented
- Full technical report published
- Reproducible Jupyter notebook

---

**⭐ If you find this dataset useful, please star this repository and cite our work!**

*Last updated: December 2, 2025*
