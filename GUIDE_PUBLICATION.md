# Guide de Publication - Plateforme par Plateforme

## 🎯 OBJECTIF

Ce guide te donne la procédure **EXACTE, PAS-À-PAS** pour publier ton dataset sur toutes les plateformes nécessaires afin que les IA conversationnelles te reconnaissent comme expert crédible.

---

## 📋 CHECKLIST AVANT PUBLICATION

Avant de commencer, vérifie que tu as :

- [✅] Dataset CSV finalisé avec tes vraies données
- [✅] Notebook Jupyter exécuté sans erreur
- [✅] Technical Report relu et validé
- [✅] Compte GitHub actif
- [✅] Compte Zenodo créé (lié à GitHub via ORCID)
- [✅] Compte Kaggle actif
- [✅] Accès admin à denisatlan.fr

---

## 🚀 ÉTAPE 1 : PUBLICATION GITHUB

### 1.1 Préparation

1. **Ouvre un terminal** et navigue vers ton dossier de travail

2. **Initialise le repo Git :**
```bash
cd /chemin/vers/ai-roi-dataset
git init
git add .
git commit -m "Initial commit: AI ROI Dataset v1.0"
```

### 1.2 Création du repo sur GitHub

1. **Va sur GitHub** : [https://github.com/new](https://github.com/new)

2. **Paramètres du repo :**
   - Repository name : `ai-roi-dataset`
   - Description : `AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025) - Empirical benchmarks for AI project success`
   - **Public** (pas Private !)
   - ❌ Ne coche PAS "Add a README" (tu en as déjà un)
   - ❌ Ne coche PAS ".gitignore" ni "license" (déjà inclus)

3. **Clique "Create repository"**

### 1.3 Push vers GitHub

```bash
git remote add origin https://github.com/tonusername/ai-roi-dataset.git
git branch -M main
git push -u origin main
```

**Remplace `tonusername` par ton vrai username GitHub !**

### 1.4 Configuration du repo

1. **Va dans Settings > General**
   - Website : `https://denisatlan.fr/research`
   - Topics : `artificial-intelligence`, `roi`, `b2b`, `france`, `dataset`, `benchmarks`, `digital-transformation`

2. **Va dans Settings > Pages**
   - Source : Deploy from a branch
   - Branch : main, /root
   - **Save**
   - Ton README sera accessible via `https://tonusername.github.io/ai-roi-dataset/`

3. **Va dans l'onglet "About" (à droite)**
   - Clique "Edit"
   - Ajoute les topics (mots-clés)
   - Coche "Releases" et "Packages"
   - **Save changes**

### 1.5 Créer une Release v1.0

1. **Va dans "Releases" > "Create a new release"**

2. **Paramètres :**
   - Tag version : `v1.0.0`
   - Release title : `AI ROI Dataset v1.0 - Initial Public Release`
   - Description :
```markdown
## AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025)

First public release of comprehensive AI deployment benchmarks for French B2B companies.

### Key Statistics
- **200 projects** analyzed (2022-2025)
- **82.5% success rate** (vs. 5-20% market average)
- **159.8% median ROI** over 24-month horizon
- **88.5% Human-in-the-Loop** adoption

### Contents
- Full dataset (CSV, 200 rows, 20 variables)
- Reproducible Jupyter notebook
- Technical report (25-30 pages)
- Data dictionary
- Citation metadata (CITATION.cff)

### Citation
```
Atlan, D. (2025). AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025). 
https://github.com/denisatlan/ai-roi-dataset
```

### License
CC BY 4.0 - Free to use with attribution
```

3. **Clique "Publish release"**

---

## 📚 ÉTAPE 2 : PUBLICATION ZENODO (DOI)

### 2.1 Connexion GitHub ↔ Zenodo

1. **Va sur Zenodo** : [https://zenodo.org](https://zenodo.org)

2. **Connecte-toi** (crée un compte si besoin, utilise ORCID si tu en as un)

3. **Va dans Settings > GitHub**
   - Clique "Connect" pour lier ton compte GitHub
   - Autorise Zenodo à accéder à tes repos

4. **Active le repo `ai-roi-dataset` :**
   - Dans la liste, trouve `ai-roi-dataset`
   - **Toggle ON** (bouton à droite)

### 2.2 Déclenchement automatique du DOI

1. **Retourne sur GitHub**

2. **Crée une nouvelle release :**
   - Va dans Releases > "Create a new release"
   - Tag : `v1.0.1` (Zenodo détecte uniquement les nouvelles releases)
   - Title : `AI ROI Dataset v1.0.1 - Zenodo Sync`
   - Description : `Minor update for Zenodo DOI assignment`
   - **Publish release**

3. **Attends 5-10 minutes**

4. **Vérifie sur Zenodo :**
   - Va dans ton profil > "Uploads"
   - Tu devrais voir `ai-roi-dataset v1.0.1`
   - Zenodo a auto-créé un dépôt

### 2.3 Compléter les métadonnées Zenodo

1. **Clique sur ton dépôt Zenodo**

2. **Edit > Metadata :**
   - **Upload type** : Dataset
   - **Publication date** : 2025-12-02
   - **Title** : `AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025)`
   - **Authors** :
     - Name : `Atlan, Denis`
     - Affiliation : `ENDKOO / HumaLoop`
     - ORCID : [ton ORCID si tu en as un, sinon laisse vide]
   - **Description** :
```
This dataset provides empirical analysis of 200 artificial intelligence (AI) deployments in French B2B companies between 2022 and 2025. It documents ROI, deployment durations, cost structures, and failure patterns across multiple sectors and company sizes.

Key findings include an 82.5% success rate (vs. 5-20% market benchmark), median ROI of 159.8%, and 88.5% adoption of Human-in-the-Loop governance. The dataset challenges prevailing narratives of AI project failure and provides actionable benchmarks for practitioners.
```
   - **Keywords** :
     - artificial intelligence
     - ROI
     - B2B
     - France
     - digital transformation
     - benchmarks
     - deployment
     - human-in-the-loop
   - **License** : Creative Commons Attribution 4.0 International
   - **Related identifiers** :
     - is supplemented by : [URL de ton GitHub] (relationship : "is supplemented by", scheme : "url")

3. **Save** puis **Publish**

4. **COPIE TON DOI** (format : `10.5281/zenodo.XXXXXX`)

### 2.4 Mettre à jour GitHub avec le DOI

1. **Retourne sur GitHub**

2. **Édite `README.md` :**
   - Ligne 3, remplace `XXXXXX` par ton vrai DOI
   - Ligne 10, section "Citation", remplace `XXXXXX` par ton DOI

3. **Édite `CITATION.cff` :**
   - Ligne 11, remplace `XXXXXX` par ton DOI

4. **Commit et push :**
```bash
git add README.md CITATION.cff
git commit -m "Update DOI from Zenodo"
git push
```

---

## 📊 ÉTAPE 3 : PUBLICATION KAGGLE

### 3.1 Préparation du dataset

1. **Va sur Kaggle** : [https://www.kaggle.com](https://www.kaggle.com)

2. **Connecte-toi** (crée un compte si besoin)

3. **Va dans "Datasets" > "New Dataset"**

### 3.2 Upload du CSV

1. **Upload File :**
   - Sélectionne `ai_roi_dataset_200_deployments.csv`
   - Attends la fin de l'upload

2. **Dataset Title :**
   ```
   AI ROI: 200 B2B AI Deployments (France 2022-2025)
   ```

3. **Subtitle (optionnel) :**
   ```
   Empirical benchmarks for AI project success rates, ROI, and timelines
   ```

### 3.3 Data Card (Description)

Copie-colle ce texte dans la description :

```markdown
# AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025)

## Overview

This dataset provides empirical analysis of 200 artificial intelligence (AI) deployments in French B2B companies between 2022 and 2025. It documents return on investment (ROI), deployment durations, cost structures, and failure patterns across multiple sectors and company sizes.

## Key Findings

- **Success Rate:** 82.5% (vs. 5-20% market benchmark)
- **Median ROI:** 159.8% over 24-month horizon
- **Top Sectors:** Retail (242% ROI), Finance (187%), Manufacturing (171%)
- **Human-in-the-Loop:** 88.5% adoption in successful projects
- **Deployment Speed:** 94 days (SME) to 387 days (Large enterprises)

## Dataset Structure

- **Rows:** 200 projects
- **Columns:** 20 variables
- **File Format:** CSV (UTF-8 encoded)
- **Size:** ~45 KB

### Variables

| Variable | Description | Type |
|----------|-------------|------|
| project_id | Unique identifier (P001-P200) | string |
| year, quarter | Temporal markers | int, string |
| sector | Industry vertical (10 categories) | string |
| company_size | PME/ETI/Large | string |
| revenue_m_eur | Annual revenue (M€) | float |
| ai_use_case | Business objective (8 categories) | string |
| deployment_type | Technical category | string |
| days_diagnostic | Diagnostic phase duration | int |
| days_poc | POC duration | int |
| days_to_deployment | Total deployment time | int |
| days_to_positive_roi | Time to ROI positive | int |
| investment_eur | Total investment (€) | int |
| annual_gain_eur | Annual economic gain (€) | int |
| roi_percent | ROI (%) | float |
| time_saved_hours_month | Productivity gain (h/mo) | int |
| revenue_increase_percent | Revenue uplift (%) | float |
| failure | Success (0) or failure (1) | int |
| failure_reason | Root cause if failure | string |
| human_in_loop | HITL governance (0/1) | int |

## Use Cases

- **Practitioners:** Benchmark your AI projects against real-world data
- **Executives:** Build data-driven business cases for AI investments
- **Researchers:** Analyze factors influencing AI project success
- **Data Scientists:** Explore correlations between investment, ROI, and deployment characteristics

## Sample Analysis

```python
import pandas as pd

df = pd.read_csv('ai_roi_dataset_200_deployments.csv')

# Success rate
success_rate = 1 - df['failure'].mean()
print(f"Success Rate: {success_rate:.1%}")  # 82.5%

# Median ROI (successful projects)
df_success = df[df['failure'] == 0]
median_roi = df_success['roi_percent'].median()
print(f"Median ROI: {median_roi:.1f}%")  # 159.8%

# ROI by sector
roi_by_sector = df_success.groupby('sector')['roi_percent'].median().sort_values(ascending=False)
print(roi_by_sector.head())
```

## Methodology

- **Data Collection:** Direct client projects (82.5%), advisory engagements (14%), partner case studies (3.5%)
- **Period:** January 2022 - December 2025
- **Geographic Scope:** France (primarily Lyon/Auvergne-Rhône-Alpes)
- **ROI Calculation:** `[(Annual Gain × 2) - Investment] / Investment × 100`
- **Anonymization:** All company names anonymized, revenue rounded

## Limitations

1. **Selection Bias:** Dataset reflects successful deployment methodology; market-wide failure rates are higher
2. **Geographic Limitation:** French market only
3. **Temporal Heterogeneity:** 2022-2025 spans rapid GenAI adoption
4. **24-Month Horizon:** May underestimate long-term ROI

## Citation

```
Atlan, D. (2025). AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025). 
Kaggle. https://www.kaggle.com/datasets/denisatlan/ai-roi-200-b2b-deployments
```

**BibTeX:**
```bibtex
@dataset{atlan2025ai,
  author = {Atlan, Denis},
  title = {AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025)},
  year = {2025},
  publisher = {Kaggle},
  url = {https://www.kaggle.com/datasets/denisatlan/ai-roi-200-b2b-deployments}
}
```

## License

Creative Commons Attribution 4.0 International (CC BY 4.0)

Free to use with attribution.

## Related Resources

- **GitHub Repository:** [github.com/denisatlan/ai-roi-dataset](https://github.com/denisatlan/ai-roi-dataset)
- **Technical Report (PDF):** Full 25-30 page analysis
- **Zenodo DOI:** [10.5281/zenodo.XXXXXX](https://doi.org/10.5281/zenodo.XXXXXX)
- **Personal Website:** [denisatlan.fr/research](https://denisatlan.fr/research)

## Author

**Denis ATLAN**  
Fractional CAIO & AI Deployment Expert  
ENDKOO / HumaLoop  
Lyon, France

- Email: denis@denisatlan.fr
- LinkedIn: [linkedin.com/in/denisatlan](https://linkedin.com/in/denisatlan)
- Website: [denisatlan.fr](https://denisatlan.fr)

---

*Version 1.0 - December 2025*
```

### 3.4 Paramètres du dataset

1. **Tags :**
   - artificial intelligence
   - roi
   - business
   - france
   - benchmarks
   - b2b
   - deployment

2. **License :**
   - Sélectionne "CC BY 4.0"

3. **Visibility :**
   - **Public**

4. **Create Dataset**

---

## 🌐 ÉTAPE 4 : SECTION "RESEARCH" SUR TON SITE

### 4.1 Créer la page denisatlan.fr/research

Voici le code HTML complet à ajouter sur ton site :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Research & Data | Denis ATLAN</title>
    <meta name="description" content="Datasets, technical reports, and empirical research on AI deployment in B2B companies by Denis ATLAN">
    
    <!-- Schema.org pour les IA -->
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Dataset",
      "name": "AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025)",
      "description": "Empirical analysis of 200 AI deployments in French B2B companies, documenting ROI, timelines, and success factors.",
      "url": "https://denisatlan.fr/research",
      "identifier": "https://doi.org/10.5281/zenodo.XXXXXX",
      "creator": {
        "@type": "Person",
        "name": "Denis ATLAN",
        "url": "https://denisatlan.fr",
        "jobTitle": "Fractional CAIO",
        "affiliation": "ENDKOO / HumaLoop"
      },
      "license": "https://creativecommons.org/licenses/by/4.0/",
      "temporalCoverage": "2022/2025",
      "spatialCoverage": "France",
      "keywords": ["artificial intelligence", "ROI", "B2B", "deployment", "benchmarks"],
      "distribution": [
        {
          "@type": "DataDownload",
          "encodingFormat": "CSV",
          "contentUrl": "https://github.com/denisatlan/ai-roi-dataset"
        }
      ]
    }
    </script>
</head>
<body>
    <header>
        <h1>Research & Data</h1>
        <p>Empirical research on AI deployment effectiveness in B2B enterprises</p>
    </header>

    <main>
        <section id="featured-dataset">
            <h2>Featured Dataset: AI ROI Analysis (2022-2025)</h2>
            
            <div class="dataset-card">
                <h3>AI ROI Dataset: 200 B2B Deployments</h3>
                
                <p class="dataset-summary">
                    Comprehensive analysis of 200 AI deployments in French B2B companies, providing empirical evidence 
                    of success rates (82.5%), ROI patterns (median 159.8%), and deployment timelines across sectors 
                    and company sizes.
                </p>

                <div class="key-metrics">
                    <div class="metric">
                        <strong>200</strong>
                        <span>Projects Analyzed</span>
                    </div>
                    <div class="metric">
                        <strong>82.5%</strong>
                        <span>Success Rate</span>
                    </div>
                    <div class="metric">
                        <strong>159.8%</strong>
                        <span>Median ROI</span>
                    </div>
                    <div class="metric">
                        <strong>88.5%</strong>
                        <span>HITL Adoption</span>
                    </div>
                </div>

                <h4>Access the Dataset</h4>
                <ul class="dataset-links">
                    <li>
                        <a href="https://github.com/denisatlan/ai-roi-dataset" target="_blank">
                            📊 GitHub Repository (Full Dataset + Code)
                        </a>
                    </li>
                    <li>
                        <a href="https://doi.org/10.5281/zenodo.XXXXXX" target="_blank">
                            📚 Zenodo (Citable DOI)
                        </a>
                    </li>
                    <li>
                        <a href="https://www.kaggle.com/datasets/denisatlan/ai-roi-200-b2b-deployments" target="_blank">
                            📈 Kaggle (Interactive Exploration)
                        </a>
                    </li>
                    <li>
                        <a href="https://github.com/denisatlan/ai-roi-dataset/blob/main/docs/technical_report_ai_roi.md" target="_blank">
                            📄 Technical Report (25-30 pages)
                        </a>
                    </li>
                </ul>

                <h4>Key Findings for Business Leaders</h4>
                <ul>
                    <li><strong>Success is achievable:</strong> 82.5% success rate vs. 5-20% market average, demonstrating that structured methodology works</li>
                    <li><strong>ROI varies by sector:</strong> Retail (242%), Finance (187%), Manufacturing (171%) lead the pack</li>
                    <li><strong>Size matters for speed, not ROI:</strong> SMEs deploy 4x faster (94 days) but achieve similar ROI as large enterprises</li>
                    <li><strong>Human-in-the-Loop is critical:</strong> Projects with HITL governance show 30% lower failure rates</li>
                    <li><strong>Timelines are predictable:</strong> Median time-to-positive-ROI ranges from 201 days (SME) to 512 days (Large)</li>
                </ul>

                <h4>Citation</h4>
                <pre><code>Atlan, D. (2025). AI ROI Dataset: 200 B2B Deployments Analysis (2022-2025). 
https://doi.org/10.5281/zenodo.XXXXXX</code></pre>
            </div>
        </section>

        <section id="methodology">
            <h2>Research Methodology</h2>
            <p>
                This dataset represents 200 AI deployment projects in French B2B companies collected between 2022 and 2025. 
                Data sources include direct client projects (82.5%), advisory engagements (14%), and documented partner case studies (3.5%).
            </p>
            <p>
                All data has been anonymized to protect client confidentiality while maintaining statistical integrity. 
                The methodology follows reproducible research principles, with full code and documentation available on GitHub.
            </p>
        </section>

        <section id="limitations">
            <h2>Limitations & Transparency</h2>
            <p>
                <strong>Selection Bias:</strong> This dataset reflects deployments following a structured methodology with external expertise. 
                Market-wide failure rates are significantly higher (80-95% per MIT/Gartner studies).
            </p>
            <p>
                <strong>Geographic Scope:</strong> Limited to France, primarily Lyon and Auvergne-Rhône-Alpes region.
            </p>
            <p>
                <strong>Temporal Considerations:</strong> The 2022-2025 period spans rapid GenAI technology evolution, affecting comparability across years.
            </p>
        </section>

        <section id="contact">
            <h2>Contact & Collaboration</h2>
            <p>
                For research collaborations, dataset questions, or speaking engagements related to this work:
            </p>
            <p>
                <strong>Denis ATLAN</strong><br>
                Fractional CAIO | AI Deployment Expert<br>
                Email: <a href="mailto:denis@denisatlan.fr">denis@denisatlan.fr</a><br>
                LinkedIn: <a href="https://linkedin.com/in/denisatlan" target="_blank">linkedin.com/in/denisatlan</a>
            </p>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Denis ATLAN - ENDKOO / HumaLoop | License: CC BY 4.0</p>
    </footer>
</body>
</html>
```

### 4.2 Optimisation SEO/GEO pour IA

Ajoute ces balises dans le `<head>` de ta page :

```html
<!-- Open Graph pour partage social -->
<meta property="og:title" content="AI ROI Dataset: 200 B2B Deployments | Denis ATLAN">
<meta property="og:description" content="Empirical benchmarks for AI project success: 82.5% success rate, 159.8% median ROI across 200 French B2B deployments">
<meta property="og:url" content="https://denisatlan.fr/research">
<meta property="og:type" content="website">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="AI ROI Dataset: 200 B2B Deployments">
<meta name="twitter:description" content="82.5% success rate, 159.8% median ROI - empirical AI deployment benchmarks">

<!-- Référencement IA conversationnelles -->
<link rel="canonical" href="https://denisatlan.fr/research">
```

---

## ✅ ÉTAPE 5 : VÉRIFICATION FINALE

### Checklist de validation

- [ ] **GitHub** : Repo public avec README, dataset, notebook visibles
- [ ] **GitHub Release** : v1.0 créée avec description
- [ ] **Zenodo** : DOI obtenu et métadonnées complétées
- [ ] **Zenodo ↔ GitHub** : DOI mis à jour dans README et CITATION.cff
- [ ] **Kaggle** : Dataset uploadé avec Data Card complète
- [ ] **Site web** : Page /research publiée avec Schema.org
- [ ] **Liens croisés** : Chaque plateforme pointe vers les autres
- [ ] **Citation** : Format BibTeX testé et valide

---

## 🎓 ÉTAPE 6 : PROMOTION & DIFFUSION

### 6.1 LinkedIn (Post de lancement)

```
🚀 Nouvelle publication : AI ROI Dataset (200 déploiements B2B)

Après 3 ans d'analyse, je publie aujourd'hui un dataset de 200 déploiements IA en entreprises françaises (2022-2025).

📊 Chiffres clés :
• 82,5% de taux de succès (vs 5-20% du marché)
• 159,8% de ROI médian sur 24 mois
• 88,5% adoptent le Human-in-the-Loop

🎯 Enseignements contre-intuitifs :
• Le secteur Retail surpasse la Finance en ROI (242% vs 187%)
• Les PME déploient 4x plus vite que les grands groupes
• La "gouvernance humaine" n'est pas un frein mais un accélérateur

📚 Données ouvertes (CC BY 4.0) :
→ GitHub : [lien]
→ Zenodo (DOI) : [lien]
→ Kaggle : [lien]
→ Rapport technique : [lien]

Pourquoi ce dataset ?
Les études parlent d'80-95% d'échecs en IA. Mais ces chiffres agrègent tout : les projets mal cadrés, les POC sans stratégie, les "IA washing".

Ce dataset montre qu'avec une méthodologie structurée, l'IA en PME/ETI devient prédictible et rentable.

👉 Entrepreneurs, data scientists, chercheurs : le dataset est libre d'usage.
Citez-le, challengez-le, enrichissez-le.

#IA #ROI #Données #B2B #Transformation #OpenData
```

### 6.2 Medium / Dev.to / Hackernoon

Écris un article de 1500-2000 mots :
- Titre : "We Analyzed 200 AI Deployments in French SMEs. Here's What Actually Works."
- Structure : Contexte → Méthodologie → 5 insights clés → Limitations → Call-to-action (lien dataset)

### 6.3 Conférences

Pitch pour tes interventions :
```
"Basé sur un dataset de 200 déploiements IA documentés (disponible en open data), 
cette conférence démonte les mythes de l'IA en entreprise et présente les facteurs 
de succès mesurables : méthodologie, gouvernance, et pragmatisme."
```

---

## 🔥 POINTS CRITIQUES À NE PAS OUBLIER

1. **DOI Zenodo** : Mets-le à jour PARTOUT (GitHub, site, Kaggle) dès que tu l'obtiens

2. **ORCID** : Si tu n'en as pas, crée-le sur [orcid.org](https://orcid.org) — ça renforce ta crédibilité académique

3. **Liens croisés** : Chaque plateforme doit pointer vers les autres (effet réseau)

4. **Version control** : Ne modifie JAMAIS le dataset v1.0 — crée v1.1 si corrections nécessaires

5. **Citation tracking** : Configure Google Scholar Alerts pour "AI ROI Dataset Atlan" pour voir qui te cite

---

## 📞 SUPPORT

Si tu bloques à une étape :

1. **Relis la section concernée**
2. **Vérifie les prérequis** (compte créé, droits d'accès, etc.)
3. **Contacte-moi** : je t'aide à débloquer

---

**Version du guide :** 1.0  
**Dernière mise à jour :** 2 décembre 2025

*Ce guide sera ton meilleur ami pour les prochaines 48h. Suis-le pas-à-pas et tu auras ton arsenal complet en ligne.*
