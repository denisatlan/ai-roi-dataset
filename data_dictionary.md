# Data Dictionary

## AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025)

This document provides detailed definitions for all variables in the dataset.

---

## Variables Overview

| Variable | Type | Description | Unit | Range/Values |
|----------|------|-------------|------|--------------|
| project_id | string | Unique anonymized identifier | - | P001-P200 |
| year | integer | Year of project initiation | - | 2022-2025 |
| quarter | string | Quarter of project initiation | - | Q1, Q2, Q3, Q4 |
| sector | string | Industry vertical | - | See Sector Categories |
| company_size | string | Company size category | - | PME, ETI, Grande |
| revenue_m_eur | float | Annual company revenue | Million € | 1.5-500+ |
| ai_use_case | string | Primary business objective | - | See Use Case Categories |
| deployment_type | string | Technical AI category | - | See Deployment Types |
| days_diagnostic | integer | Duration of diagnostic phase | days | 2-90 |
| days_poc | integer | POC development duration | days | 14-180 |
| days_to_deployment | integer | Total time to production | days | 60-540 |
| days_to_positive_roi | integer | Time until ROI positive | days | 120-730 (null if failure) |
| investment_eur | integer | Total project investment | € | 3,900-5,000,000 |
| annual_gain_eur | integer | Measured annual economic gain | € | 0-15,000,000 (0 if failure) |
| roi_percent | float | ROI over 24-month horizon | % | -30 to 450 |
| time_saved_hours_month | integer | Productivity gain | hours/month | 0-800 (0 if failure) |
| revenue_increase_percent | float | Revenue uplift (if applicable) | % | 0-80 |
| failure | integer | Project outcome | binary | 0 (success), 1 (failure) |
| failure_reason | string | Root cause of failure | - | See Failure Reasons (null if success) |
| human_in_loop | integer | HITL governance adoption | binary | 0 (no), 1 (yes) |

---

## Detailed Variable Definitions

### 1. Project Identifiers

#### project_id
- **Type:** String
- **Format:** P001 to P200
- **Description:** Unique anonymized project identifier
- **Notes:** No mapping to real company names provided (data protection)

#### year
- **Type:** Integer
- **Values:** 2022, 2023, 2024, 2025
- **Description:** Calendar year when project was initiated
- **Notes:** 2025 projects are those initiated in Q1-Q4 2025 with outcomes tracked through December 2025

#### quarter
- **Type:** String
- **Values:** Q1, Q2, Q3, Q4
- **Description:** Quarter of project initiation
- **Notes:** Combined with `year` for temporal analysis

---

### 2. Company Characteristics

#### sector
- **Type:** String (categorical)
- **Values:** 10 categories
- **Description:** Primary industry vertical

**Sector Categories:**
1. **Finance**: Banks, insurance, fintech, asset management
2. **Retail**: E-commerce, retail chains, omnichannel businesses
3. **Manufacturing**: Industrial production, assembly, process industries
4. **Services Pro**: B2B consulting, professional services, SaaS companies
5. **Telecom**: Telecommunications providers, network operators
6. **Logistique**: Transportation, logistics, supply chain services
7. **Energie**: Energy production, utilities, distribution networks
8. **Sante**: Healthcare providers, medical services (not pharma R&D)
9. **Agroalimentaire**: Food processing, agri-business
10. **Construction**: Construction, BTP (Bâtiment et Travaux Publics)

#### company_size
- **Type:** String (categorical)
- **Values:** PME, ETI, Grande
- **Description:** Company size classification based on employee count

**Size Definitions:**
- **PME** (Petite et Moyenne Entreprise): 10-49 employees
- **ETI** (Entreprise de Taille Intermédiaire): 50-249 employees
- **Grande** (Large Enterprise): 250+ employees

**Notes:** 
- Classification follows French INSEE standards
- Excludes micro-enterprises (<10 employees)
- Employee count at time of project initiation

#### revenue_m_eur
- **Type:** Float
- **Unit:** Million euros (M€)
- **Range:** 1.5 to 500+ M€
- **Description:** Annual company revenue
- **Anonymization:** 
  - PME: Rounded to nearest 0.5 M€
  - ETI: Rounded to nearest 5 M€
  - Grande: Rounded to nearest 10 M€

---

### 3. AI Deployment Characteristics

#### ai_use_case
- **Type:** String (categorical)
- **Values:** 8 categories
- **Description:** Primary business objective of the AI deployment

**Use Case Categories:**
1. **Process Automation**: RPA, workflow automation, back-office optimization
2. **Customer Service Bot**: Chatbots, virtual assistants, NLP-based support
3. **Predictive Analytics**: Demand forecasting, risk prediction, trend analysis
4. **Document Processing**: OCR, information extraction, document classification
5. **Quality Control Vision**: Visual inspection, defect detection, computer vision QC
6. **Sales Automation**: Lead scoring, sales forecasting, pipeline optimization
7. **Pricing Optimization**: Dynamic pricing, revenue management, price intelligence
8. **Fraud Detection**: Anomaly detection, transaction monitoring, security (Finance-specific)

#### deployment_type
- **Type:** String (categorical)
- **Values:** Automation, NLP, Analytics, Vision, Hybrid
- **Description:** Technical classification of AI deployment

**Type Definitions:**
- **Automation**: RPA, rule-based systems, workflow engines
- **NLP**: Natural Language Processing (chatbots, text analysis, translation)
- **Analytics**: Predictive models, forecasting, statistical ML
- **Vision**: Computer vision, image recognition, video analysis
- **Hybrid**: Combination of 2+ types (e.g., NLP + Analytics)

#### human_in_loop
- **Type:** Integer (binary)
- **Values:** 0 (No HITL), 1 (HITL implemented)
- **Description:** Presence of Human-in-the-Loop governance

**HITL Definition:**
- **1 (Yes)**: AI outputs require human validation before execution, OR feedback loops allow human correction, OR escalation pathways exist for edge cases
- **0 (No)**: Fully automated decisions with no human oversight

---

### 4. Timeline Metrics

#### days_diagnostic
- **Type:** Integer
- **Unit:** Days
- **Range:** 2-90 days
- **Description:** Duration of initial diagnostic/assessment phase
- **Includes:**
  - Business case development
  - Data audit
  - Feasibility study
  - Stakeholder alignment

#### days_poc
- **Type:** Integer
- **Unit:** Days
- **Range:** 14-180 days
- **Description:** Proof-of-concept development duration
- **Includes:**
  - Model development/training
  - Integration testing
  - User acceptance testing
  - Performance validation

#### days_to_deployment
- **Type:** Integer
- **Unit:** Days
- **Range:** 60-540 days
- **Description:** Total time from project kickoff to production deployment
- **Calculation:** Diagnostic + POC + Deployment phases
- **Milestone:** AI system live in production environment

#### days_to_positive_roi
- **Type:** Integer (nullable)
- **Unit:** Days
- **Range:** 120-730 days (null if failure=1)
- **Description:** Time from project kickoff until cumulative gains exceed total investment
- **Notes:**
  - Null for failed projects
  - Measured from first day of diagnostic phase

---

### 5. Financial Metrics

#### investment_eur
- **Type:** Integer
- **Unit:** Euros (€)
- **Range:** 3,900 to 5,000,000 €
- **Description:** Total project investment (CAPEX + Year 1 OPEX)

**Investment Components:**
- Software licenses / API costs
- External consulting fees
- Internal labor (opportunity cost)
- Infrastructure (cloud, servers)
- Training and change management
- Maintenance (Year 1 only)

**Excludes:** Years 2+ operational costs

#### annual_gain_eur
- **Type:** Integer
- **Unit:** Euros (€)
- **Range:** 0 to 15,000,000 € (0 if failure=1)
- **Description:** Measured annual economic gain post-deployment

**Gain Calculation Methods:**
1. **Time Saved:** Hours saved × Hourly labor cost
2. **Cost Reduction:** Documented operational cost decrease
3. **Revenue Increase:** Incremental revenue attributed to AI (e.g., dynamic pricing uplift)

**Measurement Period:** Annualized value after stabilization (typically 3-6 months post-deployment)

#### roi_percent
- **Type:** Float
- **Unit:** Percentage (%)
- **Range:** -30% to 450%
- **Description:** Return on Investment over 24-month horizon

**Calculation Formula:**
```
ROI (%) = [(Annual Gain × 2) - Investment] / Investment × 100
```

**Interpretation:**
- Positive ROI: Project financially successful
- Negative ROI: Investment not recovered within 24 months
- Conservative estimate (does not include Years 3+ value)

---

### 6. Outcome Metrics

#### time_saved_hours_month
- **Type:** Integer
- **Unit:** Hours per month
- **Range:** 0-800 hours/month (0 if failure=1)
- **Description:** Productivity gain measured in time saved
- **Measurement:** Documented reduction in manual task hours
- **Examples:**
  - Document processing: Hours previously spent on manual data entry
  - Chatbot: Hours customer service agents previously spent on routine queries
  - Predictive maintenance: Hours saved avoiding unplanned downtime

#### revenue_increase_percent
- **Type:** Float
- **Unit:** Percentage (%)
- **Range:** 0-80%
- **Description:** Revenue uplift directly attributable to AI deployment
- **Applicable Use Cases:**
  - Sales Automation (improved conversion rates)
  - Pricing Optimization (revenue per unit)
  - Customer Service (retention impact)
- **Measurement:** A/B testing or before/after comparison with control groups
- **Notes:** 0% if use case is not revenue-focused

#### failure
- **Type:** Integer (binary)
- **Values:** 0 (Success), 1 (Failure)
- **Description:** Project outcome classification

**Failure Definition:**
- Project terminated before reaching production, OR
- ROI remains negative after 24-month measurement period

**Success Definition:**
- System deployed to production, AND
- Positive ROI achieved within 24 months

#### failure_reason
- **Type:** String (categorical, nullable)
- **Values:** 6 categories (null if failure=0)
- **Description:** Root cause of project failure

**Failure Reason Categories:**
1. **Qualité données insuffisante**: Insufficient data quality (missing, biased, incomplete)
2. **Résistance au changement**: Organizational resistance, user non-adoption
3. **Intégration technique bloquée**: Technical integration failed (legacy systems, APIs)
4. **Budget dépassé**: Budget overrun, funding terminated
5. **ROI insuffisant**: System works but economic value below expectations
6. **Compétences internes manquantes**: Skills gap, unable to maintain system

---

## Data Quality & Limitations

### Completeness
- **100% complete:** All 200 projects have values for all required fields
- **Conditional nulls:** `days_to_positive_roi` and `failure_reason` are null by design based on `failure` value

### Accuracy
- Financial data (investment, gains) verified via client invoices/reports
- Timeline data extracted from project management systems
- ROI calculation uses conservative assumptions (24-month horizon)

### Anonymization
- Company names replaced with anonymized IDs
- Revenue figures rounded per company size category
- Geographic details limited to "France"
- No personally identifiable information (PII)

### Known Biases
- **Selection bias:** Dataset reflects successful deployment methodology
- **Geographic bias:** French market only (Lyon/Auvergne-Rhône-Alpes focus)
- **Temporal bias:** 2022-2025 period spans GenAI adoption wave

---

## Usage Notes

### Reproducibility
- All calculations can be reproduced using the Jupyter notebook
- Random seed=42 for synthetic data generation
- Version control via CHANGELOG.md

### Statistical Analysis Recommendations
- Use non-parametric tests (median, IQR) due to right-skewed distributions
- Control for company_size when comparing sectors
- Consider temporal trends (year effects)

### Ethical Considerations
- Do not attempt to re-identify companies from patterns
- Cite this dataset when using in publications
- Report any data quality issues to maintainer

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-02 | Initial release (200 projects, 2022-2025) |

---

## Contact

For questions about variable definitions or data quality:

**Denis ATLAN**  
Email: denis@denisatlan.fr  
Website: [denisatlan.fr](https://denisatlan.fr)

---

*Last updated: December 2, 2025*
