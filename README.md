
# FHIR Patient Explorer

## Overview
A Python-based pipeline that queries a live FHIR R4 server, parses 
Patient and Observation resources into structured DataFrames, and 
visualizes clinical observation patterns across lab and vital sign categories.

Built as part of a Health IT / Informatics portfolio to demonstrate 
real-world FHIR API integration.

## What this project does
- Connects to a public FHIR R4 sandbox (HAPI FHIR server)
- Pulls Patient demographic data and Observation resources via REST API
- Parses nested FHIR JSON into clean pandas DataFrames
- Identifies LOINC-coded observation types and their frequency
- Visualizes observation category distribution (laboratory vs vital signs)

## Key findings
- 83% of observations were laboratory results; 17% vital signs
- Most frequent lab markers: HbA1c, LDL cholesterol, triglycerides, 
  creatinine, glucose — core cardiometabolic risk indicators
- Most common conditions: hypertension, diabetes, asthma
- Coding completeness varied by resource: Conditions ~88% coded, 
  Observations ~56%, Medications ~46% — highlights real-world data 
  quality challenges in production EHR systems
- Dataset contained multilingual entries (English, Spanish, German) 
  demonstrating FHIR's international interoperability in practice
- Medication coding mixed RxNorm and SNOMED-CT systems — 
  common inconsistency in real FHIR implementations

## Technologies used
- Python (requests, pandas, matplotlib)
- FHIR R4 (HL7 standard)
- HAPI FHIR public sandbox (hapi.fhir.org)
- LOINC terminology for observation coding

## How to run
1. Clone this repo
2. pip install requests pandas matplotlib
3. Open notebooks/01_fhir_patient_explorer.ipynb
4. Run all cells — no API key required (uses public sandbox)

## Project structure
notebooks/
  01_fhir_patient_explorer.ipynb  ← main analysis notebook
outputs/
  figures/
    fhir_observations.png         ← observation type visualization

## About
Part of a Health IT portfolio focused on FHIR interoperability, 
clinical data pipelines, and real-world evidence generation.
Author: Nikhitha Chaparla | Saint Louis University, M.S. Health Informatics
