# Clinical-Data-Management-Portfolio
## Dental OPD Data Management Project
This project demonstrates an Excel-based system for managing Dental OPD (Outpatient Department) records, focusing on data integrity, patient tracking, and workflow efficiency.


### Key Features Covered:
* Patient demographics and visit log management.
* Automated data validation and tracking formulas.
* Clean formatting compliant with data entry standards.
### 📥 Project Files & Download
* 💾 **Source Dataset:** [Download SnehaP_Dental_OPD_Excel_Sample.xlsx](SnehaP_Dental_OPD_Excel_Sample.xlsx)

---

### 💻 Project Walkthrough & Visuals

#### 1. Master Data Log
This is the main clinical database tracking patient registration, demographics, and initial department routing while maintaining clinical data consistency.
![Dental OPD LOG](Dental%20OPD%20LOG.png)

#### 2. Data Entry & Input Guide
To prevent errors during active clinical operations, this input guide provides strict data validation constraints and user guidance for team members inputting patient records.
![Dental OPD INPUT GUIDE](DENTAL%20OPD%20INPUT%20GUIDE.png)

#### 3. Analytics & Summaries
These reporting dashboards aggregate clinical trends, tracking daily patient metrics to optimize clinic workflow and resource management.

**Key Performance Metrics:**
![Dental OPD Summary 1](DENTAL%20OPD%20SUMMARY%201.png)

**Operational Trends:**
![Dental OPD Summary 2](DENTAL%20OPD%20SUMMARY%202.png)


---

# Clinical Trial EDC Validation & Edit Check Specification Project
This project covers the complete Data Entry Guidelines (DEG) and Data Validation Specifications (Edit Checks) for a Phase 1/2 Clinical Trial CRF (Protocol: CTJ301UC201).
### Key Features Covered:
* **CRF Field Identification**: Mapping CDISC-compliant domain variables for Screening Demographics (`DM`) and Routine Labs (`RH`, `RCC`).
* **Format & Type Validation**: Strict rules for entry formats (e.g., DD/MM/YY date formats, numeric limits, decimal allowances).
* **Automated Query Logic**: Range-check specifications and cross-form edit checks (e.g., sex-specific reference ranges for Hematocrit & Hemoglobin).
### 📩 Project Files & Download
* 📄 **Full Edit Check Document:** [Download CLINICAL TRIAL EDC VALIDATION &EDIT CHECK SPECIFICATION PROJECT](./CLINICAL%20TRIAL%20EDC%20VALIDATION%20&EDIT%20CHECK%20SPECIFICATION%20PROJECT.pdf)

---

### Edit Check Specification Overview:
#### 1. Demographics Domain (DM)
* **Gender (`DM_GD`)**: Single-select options (`0 = Male`, `1 = Female`). Missing selection triggers an automated query.
* **Date of Birth (`DM_DOB`)**: Strict 6-digit numeric date format (`DD/MM/YY`). Alphabet/decimal or missing entries trigger queries.
* **Race (`DM_RC`) & Ethnic Origin (`DM_EO`)**: Standardized mapping to Caucasians, Black, Oriental, Asian, White, Indigenous, Hispanic, and Latino categories.
#### 2. Routine Haematology Domain (RH)
* **Sex-Specific Logic**: Cross-form edit check checks `DM_GD` to set dynamic range checks:
  * **Hematocrit (`RH_HCT`)**: Males: 41–50% | Females: 36–44%. Raises query if Male = 40 or Female = 35.
  * **Hemoglobin (`RH_HB`)**: Males: 13.5–16.0 g/dL | Females: 12.5–14.5 g/dL.
* **Numeric Boundary Checks**: Strict min/max triggers for Differential WBC Counts (Neutrophils, Lymphocytes, Monocytes, Eosinophils, Basophils)
#### 3. Routine Clinical Chemistry Domain (RCC)
* **Liver & Renal Panels**: Automated range queries configured for ALT, AST, Alkaline Phosphatase, Bilirubin, Creatinine, and Blood Glucose.
* **Conditional Logic**: `Bilirubin – Direct (RCC_BRD)` field generation is dynamically triggered only if `Bilirubin – Total (RCC_BRT)` is outside the reference range (0.3–1.2 mg/dL).

 
