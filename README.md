# Digital Fraud Intelligence
### Exploratory Analysis of Cybercrime Patterns and Regional Trends in India

**EDAV course end project** | Python · NumPy · Pandas · Matplotlib · Seaborn

> This repository analyses officially reported cybercrime statistics. It does **not** claim to represent every fraud that occurred, individual victims, or individual transactions.

## Research focus
This project investigates how recorded cybercrime varies across years, Indian states/UTs and offence classifications. It distinguishes broad crime heads, specific crime types and motive classifications rather than treating them as interchangeable measures.

### Research questions
1. How have recorded cybercrime counts changed over the available years?
2. Which states/UTs have the largest recorded counts, and how does the ranking change by year?
3. Which offence classifications account for the largest recorded counts?
4. Are there visible shifts in the composition of recorded cybercrime over time?
5. How do state-year crime-head summaries compare with state-year motive summaries, when the optional second dataset is available?

## Data sources
The notebook expects source CSVs downloaded from these dataset pages:

| File expected | Source | Coverage / grain |
|---|---|---|
| `data/raw/ncrb_state_crime_head.csv` | [NCRB cyber crimes: year, state and crime-head dataset (Dataful)](https://dataful.in/datasets/22359/) | 2002–2023; year, state and offence classification; 22,042 rows listed by source |
| `data/raw/ncrb_state_motive.csv` *(optional)* | [NCRB cyber crimes: year, state and motive dataset (Dataful)](https://dataful.in/datasets/22361/) | Year, state and recorded motive classification |
| Official source institution | [National Crime Records Bureau](https://ncrb.gov.in/) | Original statistical source |

Dataful republishes NCRB-derived tables and exposes downloadable CSV/XLSX/Parquet formats. Download the CSV from the linked dataset page and save it using the exact filename shown above. The notebook checks the columns and stops with a useful message if the file is missing or its schema is incompatible.

**Important:** Dataful is the distribution page; NCRB is the originating statistical institution. Cite both in your submission.

## Repository layout
```text
Digital-Fraud-Intelligence-EDAV/
├── README.md
├── requirements.txt
├── .gitignore
├── LICENSE
├── data/
│   ├── raw/                 # Download source CSVs here; not committed by default
│   └── processed/           # Generated clean datasets
├── notebooks/
│   └── Digital_Fraud_Intelligence_EDAV.ipynb
├── outputs/
│   ├── figures/             # Generated charts
│   └── tables/              # Generated summaries
└── docs/
    ├── COURSE_OUTCOME_MAPPING.md
    └── METHODOLOGY.md
```

## Run the project
1. Download the primary CSV from the [NCRB state-wise cybercrime dataset page](https://dataful.in/datasets/22359/).
2. Save it as `data/raw/ncrb_state_crime_head.csv`.
3. *(Optional)* Download the state-wise motive CSV from [dataset 22361](https://dataful.in/datasets/22361/) and save it as `data/raw/ncrb_state_motive.csv`.
4. Create an environment and install dependencies:
   ```bash
   python -m venv .venv
   # Windows: .venv\Scripts\activate
   # macOS/Linux: source .venv/bin/activate
   pip install -r requirements.txt
   jupyter notebook
   ```
5. Open and run `notebooks/Digital_Fraud_Intelligence_EDAV.ipynb` from the repository root.
6. Review generated tables and figures in `outputs/`.

## Data integrity and interpretation rules
- Do not add totals from different classification dimensions (crime head, crime type, motive) together.
- Check whether rows labelled `Total` overlap with their component categories before aggregating. The notebook uses explicit filtering and reports its choices.
- Reported cases are not the same as prevalence. Changes can reflect reporting behaviour, law, classification, police registration and underlying incidence.
- Do not infer causation from descriptive associations.
- Do not describe state totals as risk rates unless a compatible population denominator and matching year are supplied.
- The optional motive data is analysed as a separate classification dimension. A state-year join is a side-by-side comparison, not a combined count.

## Course outcome coverage
See [docs/COURSE_OUTCOME_MAPPING.md](docs/COURSE_OUTCOME_MAPPING.md) for the CO1–CO5 mapping and the exact notebook sections.

## Limitations
The source is aggregated. It does not provide individual victim demographics, victim-level behaviour, transaction IDs, payment instruments, amounts lost per person, recovery outcomes or exact scam narratives. The project title and conclusions therefore focus on **reported cybercrime patterns**, not unsupported victim-level behavioural claims.

## Author
**Charan**  
EDAV Course End Project
