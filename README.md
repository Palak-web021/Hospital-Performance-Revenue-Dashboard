# Interactive KPI Dashboard Development

## Project contents
- `data/`: five cleaned CSV files ready for Power BI import.
- `powerbi_assets/DAX_Measures.dax`: starter DAX measures.
- `powerbi_assets/Power_Query_Import_Template.m`: folder-import template (edit FolderPath).
- `powerbi_assets/relationships_and_layout.md`: model and report build guide.
- `dashboard_preview.png`: visual design reference.

## Data preparation performed
- Removed direct identifiers and unnecessary sensitive fields from the patient fact table:
  full name, date of birth, religion, phone number, street address and town/village.
- Removed repeated descriptive columns that are available in dimension tables.
- Trimmed whitespace in text fields and standardized missing insurance values as
  `Uninsured / Not recorded`.
- Kept the pseudonymous patient_id for distinct counting and row-level analysis.
- Retained the original five-table structure and source row counts.

## Data note
The patient table contains 500,000 rows. The source contains synthetic-looking
and potentially inconsistent business values; this project preserves source measures
rather than silently rewriting them. Validate unusual values before presenting findings
as real-world healthcare conclusions. Do not publish patient-level records publicly.

## Quick start
1. Extract this ZIP.
2. In Power BI Desktop, use Get Data > Text/CSV to import each CSV in `data/`.
3. Rename tables exactly: `Patients`, `Hospitals`, `Diagnosis`, `Procedures`, `Medications`.
4. Create relationships using the guide in `powerbi_assets/relationships_and_layout.md`.
5. Add measures from `powerbi_assets/DAX_Measures.dax`.
6. Build report pages using the dashboard preview and layout guide.
