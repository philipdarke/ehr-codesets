# Drug code sets for Electronic Health Record research

:warning: UK Biobank [guidance](https://biobank.ndph.ox.ac.uk/showcase/ukb/docs/primary_care_data.pdf) highlights issues including incomplete and/or inconsistently formatted BNF codes, missing Read v2 codes and missing drug names. The [ukbb-ehr-data repository](https://github.com/philipdarke/ukbb-ehr-data/) includes example code to handle these issues and identify periods of prescriptions using the code sets below.

## Drug coding

[prescriptions.rds](drugs/prescriptions.rds) is a named "list of lists" for the following drug categories:

Drug category | Name
------------- | ---------
Anti-diabetes drugs | `diabetes`
Anti-hypertensives | `hypertension`
Atypical anti-psychotics | `antipsychotic`
Steroids | `steroids`
Statins | `statins`

For each drug category the following codes are provided:

Name | Description
--------- | -----------
`read` | Read v2 codes for the drug category. Partial matching should be used e.g. `bxi` means select all Read v2 codes starting `bxi` (those matching the regular expression `^bxi`).
`bnf` | BNF codes for the drug category. Partial matching should be used e.g. `0212000AA` means select all Read v2 codes starting `0212000AA` (those matching the regular expression `^0212000AA`).
`search` | Search terms that can be used to identify drugs based on the `drug_name` field. E.g. `statin` means select any drug matching the regular expression `statin` (case insensitive).

Search terms aim to cover all potential generic and brand names for drugs in each category. Results should be carefully reviewed when using these terms.

## Anti-diabetes drugs

Codes are provided for:

Drug category | Name
------------- | ---------
Any anti-diabetes drug | `all`
Insulin | `insulin`
All anti-diabetic drugs excluding insulin | `non_insulin`
Metformin | `metformin`

For the avoidance of doubt, metformin codes are included under `non_insulin`.

For example, the following returns BNF codes for anti-diabetes drugs:

```R
drug_codes <- readRDS("drugs/prescriptions.rds")
drug_codes$diabetes$all$bnf  # codes for all anti-diabetes drugs
drug_codes$diabetes$insulin$bnf  # codes for insulin only
```

## Anti-hypertensives

Codes are provided for:

Drug category | Name
------------- | ---------
Any anti-hypertensive | `all`
Thiazides and related diuretics | `thiazides`
Potassium-sparing diuretics and aldosterone antagonists | `potassium_aldosterone`
Potassium sparing diuretics and compounds | `potassium_compounds`
Beta adrenoceptor blocking drugs | `beta_blockers`
Vasodilator antihypertensive drugs | `vasodilator`
Centrally-acting antihypertensive drugs | `centrally_acting`
Adrenergic neurone blocking drugs | `adrenergic_blockers`
Alpha-adrenoceptor blocking drugs | `alpha_blockers`
Renin-angiotensin system drugs | `renin_system`
Calcium-channel blockers | `calcium_blockers`

For example, the following returns Read v2 codes for anti-hypertensives:

```R
drug_codes <- readRDS("drugs/prescriptions.rds")
drug_codes$hypertension$all$read  # codes for all anti-hypertensives
drug_codes$hypertension$vasodilator$read  # codes for vasodilators only
```


## Atypical anti-psychotics

The following returns the search terms for all atypical anti-psychotics including depot injections:

```R
drug_codes <- readRDS("drugs/prescriptions.rds")
drug_codes$antipsychotic$all$search
```

## Steroids

The following returns BNF codes for all steroids including depot injections:

```R
drug_codes <- readRDS("drugs/prescriptions.rds")
drug_codes$steroids$all$bnf
```

## Statins

The following returns Read v2 codes for all statins:

```R
drug_codes <- readRDS("drugs/prescriptions.rds")
drug_codes$statins$all$read
```
