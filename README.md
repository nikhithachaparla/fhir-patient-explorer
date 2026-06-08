
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
- 83% of observations in the dataset were laboratory results; 
  17% were vital signs — consistent with real-world EHR documentation patterns
- Most frequent lab markers included HbA1c, LDL cholesterol, triglycerides, 
  creatinine, and plasma glucose — core cardiometabolic risk indicators
- Dataset contained multilingual entries (English and Spanish LOINC displays), 
  demonstrating FHIR's international interoperability in practice

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
