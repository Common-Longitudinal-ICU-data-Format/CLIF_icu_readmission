# ICU Readmission

## Objective

Identify ICU readmission events using the Common Longitudinal Intensive Format (CLIF) 2.0 data structure

## Required CLIF tables and fields

Please refer to the online [CLIF data dictionary](https://clif-consortium.github.io/website/data-dictionary.html), [ETL tools](https://github.com/clif-consortium/CLIF/tree/main/etl-to-clif-resources), and [specific table contacts](https://github.com/clif-consortium/CLIF?tab=readme-ov-file#relational-clif) for more information on constructing the required tables and fields. List all required tables for the project here, and provide a brief rationale for why they are required.

To identify ICU readmission:
1. **patient**: `patient_id`, `race_category`, `ethnicity_category`, `sex_category`, 'death_dttm'
2. **hospitalization**: `patient_id`, `hospitalization_id`, `admission_dttm`, `discharge_dttm`, `age_at_admission`
3. **adt**: 'patient_id',`hospitalization_id`, `in_dttm`, 'out_dttm', 'location_name', 'location_category'

## Important definitions
1. Definition of ICU readmission: Any return to ICU after index ICU discharge, during the same hospitalization. (E.g., ICU --> Ward --> ICU, ICU --> Ward --> Other Hospital Area --> ICU)
2. Definition of Planned ICU readmission: Any ICU readmissions that is directly associated with a scheduled procedure or intervention (E.g., ICU --> procedure --> ICU)
3. Definition of Unplanned ICU readmission: Any ICU readmissions that exclude planned ICU readmissions 

## Cohort identification
Study period: January 1, 2020 to December 31, 2021 (2 years)
Inclusion criteria:
   1) Patients with at least one ICU admission during the study period (2020-2021)
   2) Age >= 18 years at the time of initial hospital admission

Exclusion crtieria: 
   1) Patients who died during their index ICU stay.
   2) Patients who were discharged immediately after their index ICU stay. 

## Expected Results
Describe the output of the analysis. The final project results should be saved in the [`output/final`](output/README.md) directory.

## Detailed Instructions for running the project

## 1. Setup Project Environment
Describe the steps to setup the project environment. 

Example for Python:
```
python3 -m venv .mobilization
source .mobilization/bin/activate
pip install -r requirements.txt 
```

## 2. Update `config/config.json`
Follow instructions in the [config/README.md](config/README.md) file for detailed configuration steps.

## 3. Run code
Detailed instructions on the code workflow are provided in the [code directory](code/README.md)
---


