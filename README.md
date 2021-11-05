# Code sets for Electronic Health Record research

Primary and secondary care code sets for Electronic Health Record research. The code sets were developed primarily for use with UK Biobank data.

## Primary care

Clinical event codes are provided using Read v2 and Clinical Terms Version 3 (CTV3) classifications.

### Conditions ([csv](primary_care/conditions.csv)/[rds](primary_care/conditions.rds))

Variable | Value | Level | Description
-------- | ----- | ----- | -----------
`angina` | `diagnosis` | `stable` | Stable angina
`angina` | `diagnosis` | `unstable` | Unstable angina
`bipolar` | `diagnosis` | `-` | Bipolar disorder
`diabetes` | `diagnosis` | `-` | Diabetes (type unknown)
`diabetes` | `diagnosis` | `type1` | Type 1 diabetes
`diabetes` | `diagnosis` | `type2` | Type 2 diabetes
`diabetes` | `diagnosis` | `gestational` | Gestational diabetes
`diabetes` | `diagnosis` | `secondary` | Secondary diabetes
`diabetes` | `diagnosis` | `remission` | Diabetes remission
`diabetes` | `diagnosis` | `resolved` | Diabetes resolution
`diabetes` | `family_history` | `-` | Family history of diabetes
`hypertension` | `diagnosis` | `-` | Hypertension
`learning_disabilities` | `diagnosis` | `-` | Learning disabilities
`mi` | `diagnosis` | `-` | Myocardial infarction/heart attack
`pcos` | `diagnosis` | `-` | Polycystic ovarian syndrome
`schizophrenia` | `diagnosis` | `-` | Schizophrenia
`stroke` | `diagnosis` | `haemorrhagic` | Haemorrhagic stroke
`stroke` | `diagnosis` | `ischaemic` | Ischaemic stroke
`tia` | `diagnosis` | `-` | Transient ischaemic attack

### Biomarkers ([csv](primary_care/biomarkers.csv)/[rds](primary_care/biomarkers.rds))

Variable | Value | Level | Description
-------- | ----- | ----- | -----------
`blood_glucose` | `fpg` | `-` | Fasting plasma glucose
`blood_glucose` | `hba1c` | `-` | Glycated hemoglobin
`blood_glucose` | `ogtt` | `2hour` | 2 hour oral glucose tolerance test
`blood_glucose` | `random` | `-` | Random blood sugar
`blood_glucose` | `unknown` | `-` | Glucose test (unknown type)
`anthropometric` | `bmi` | `-` | Body mass index
`anthropometric` | `height` | `-` | Height
`anthropometric` | `weight` | `-` | Weight
`anthropometric` | `waist` | `-` | Waist circumference

### Demographic/other ([csv](primary_care/other.csv)/[rds](primary_care/other.rds))

Variable | Value | Level | Description
-------- | ----- | ----- | -----------
`smoking` | `current` | `trivial` | Current trivial smoker
`smoking` | `current` | `light` | Current light smoker
`smoking` | `current` | `moderate` | Current moderate smoker
`smoking` | `current` | `heavy` | Current heavy smoker
`smoking` | `current` | `very_heavy` | Current very heavy smoker
`smoking` | `current` | `-` | Current smoker (level unknown)
`smoking` | `former` | `trivial` | Former trivial smoker
`smoking` | `former` | `light` | Former light smoker
`smoking` | `former` | `moderate` | Former moderate smoker
`smoking` | `former` | `heavy` | Former heavy smoker
`smoking` | `former` | `very_heavy` | Former very heavy smoker
`smoking` | `former` | `-` | Former smoker (level unknown)
`smoking` | `never` | `-` | Never smoked
`smoking` | `non` | `-` | Non-smoker (assumed current)
`smoking` | `passive` | `-` | Passive smoker (assumed current)
`smoking` | `consumption` | `-` | Cigarette consumption

## Drug prescriptions

Around 76% of UK Biobank prescription records have a BNF code. 99.7% of records have a BNF and/or Read v2 code. Prescription codes are therefore provided using British National Formulary (BNF) and Read v2 classifications.

[prescriptions.rds](drugs/prescriptions.rds) is a named "list of lists" for the following drug categories:

Drug category | Name
------------- | ---------
Anti-diabetes drugs | `diabetes`
Anti-hypertensives | `hypertension`
Atypical anti-psychotics | `antipsychotic`
Steroids | `steroids`
Statins | `statins`

**Further details are provided [here](drugs/README.md).**

:warning: UK Biobank [guidance](https://biobank.ndph.ox.ac.uk/showcase/ukb/docs/primary_care_data.pdf) highlights issues including incomplete and/or inconsistently formatted BNF codes, missing Read v2 codes and missing drug names. The [ukbb-ehr-data repository](https://github.com/philipdarke/ukbb-ehr-data/) includes example code to handle these issues and extract drugs using these code sets.

## Secondary care

Secondary care diagnoses are provided using ICD-9 and ICD-10 coding classifications. Procedures are provided using OPCS-3 and OPCS-4 classifications.

### Conditions ([csv](secondary_care/conditions.csv)/[rds](secondary_care/conditions.rds))

Variable | Value | Level | Description
-------- | ----- | ----- | -----------
`diabetes` | `diagnosis` | `-` | Diabetes (type unknown)
`diabetes` | `diagnosis` | `type1` | Type 1 diabetes
`diabetes` | `diagnosis` | `type2` | Type 2 diabetes
`diabetes` | `diagnosis` | `gestational` | Gestational diabetes
`diabetes` | `diagnosis` | `secondary` | Secondary diabetes

## Other resources

### Open repositories

The majority of diagnosis records in the [interim EHR data release](https://biobank.ndph.ox.ac.uk/showcase/ukb/docs/primary_care_data.pdf) use the CTV3 coding classification. The code set repositories below typically only cover Read v2 diagnostic codes and limited prescription coding.

* https://phenotypes.healthdatagateway.org/
* https://www.opencodelists.org/
* https://clinicalcodes.rss.mhs.man.ac.uk/
* https://caliberresearch.org/portal is no longer updated

[Kuan et al](https://doi.org/10.1016/S2589-7500(19)30012-3) (2019) includes a map of 308 physical and mental health conditions. Read v2 codes are available at [CALIBER](https://caliberresearch.org/portal) and https://github.com/spiros/chronological-map-phenotypes.

### Prescription coding

* https://openprescribing.net/bnf/ includes a browsable BNF with high-level prescribing trends
* https://www.thedatalab.org/blog/161/prescribing-data-bnf-codes/ summarises the BNF coding structure

### Code mapping

* https://biobank.ndph.ox.ac.uk/showcase/refer.cgi?id=592
* https://isd.digital.nhs.uk/

## Licence

Made available under a [Creative Commons Attribution 4.0 International License](https://github.com/philipdarke/ehr-codesets/blob/master/LICENSE).
