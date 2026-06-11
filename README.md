# Grype Vulnerability Report Automation

## Overview

This project automates the processing of Grype vulnerability scan results.

The solution reads a Grype JSON report, extracts vulnerability information, and generates a structured Excel report for vulnerability analysis and remediation tracking.

---

## Technologies Used

* Python
* Docker
* Grype
* Pandas
* OpenPyXL

---

## Workflow

1. Scan a Docker image using Grype.
2. Export results in JSON format.
3. Parse the JSON file using Python.
4. Extract:

   * Package Name
   * Package Version
   * CVE ID
   * Severity
5. Generate an Excel report.

---

## Example Usage

Generate Grype JSON report:

```bash
grype image_name -o json > results.json
```

Run the automation:

```bash
python scan.py
```

Output:

```text
grype_report.xlsx
```

---

## Docker Usage

Build the image:

```bash
docker build -t grype_scan:v1 .
```

Run the container:

```bash
docker run --rm grype_scan:v1
```

---

## Sample Output

| Package    | Version  | CVE            | Severity |
| ---------- | -------- | -------------- | -------- |
| python     | 3.12.13  | CVE-2026-6100  | Critical |
| libcrypto3 | 3.5.6-r0 | CVE-2026-45447 | High     |

---

## Author

Adnan Shboul

Application Security | Container Security | Security Automation
