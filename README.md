
# Equity Trade Data Quality Framework
**Building Trust in Equity Trade Submissions**

---

## 1. Project Overview
This framework was developed to validate and ensure the integrity of equity trade data submitted under UK financial regulations.  
It automates schema, business, and regulatory checks to ensure all trade submissions to the **Financial Conduct Authority (FCA)** meet **MiFID II** standards.

After three validation cycles, the framework achieved a **98% reliability score**, confirming its readiness for production deployment and audit inspection.

---

## 2. Purpose & Benefits
Trade reporting errors — such as invalid ISINs, zero quantities, or incorrect timestamps — can lead to:
- Regulatory breaches and resubmission penalties  
- Increased operational risk  
- Reputational damage  

This framework helps clients and partners:
- Detect and resolve trade data issues before submission  
- Automate compliance checks and reduce manual QA  
- Improve audit readiness and transparency  
- Strengthen trust in downstream reporting systems  

---

## 3. Integration & Compatibility
| Category | Details |
|-----------|----------|
| **Data Sources** | Trade systems, data lakes |
| **Formats Supported** | CSV + JSON metadata |
| **Delivery Method** | Secure SFTP submission to FCA |
| **Validation Configs** | YAML-based, customizable |
| **Audit Logs** | Stored and versioned for inspection |

---

## 4. Report Scope & Submission Standards
| Field | Description |
|--------|-------------|
| **Report Name** | Equity Trade Activity Report |
| **Regulator** | UK Financial Conduct Authority (FCA) |
| **Frequency** | Daily (T+1) |
| **Format** | CSV with JSON metadata |
| **Delivery Method** | Secure SFTP submission |
| **Owner** | Trading & Compliance Division |

The Equity Trade Activity Report captures all executed trades across markets and must reflect accurate trade details for downstream compliance systems.

---

## 5. Schema Description
| Field Name | Data Type | Description | Regulatory Requirement |
|-------------|------------|-------------|--------------------------|
| Trade_ID | String | Unique trade identifier | Mandatory |
| ISIN | String | Instrument identifier for equity | Must match FCA reference |
| Price | Decimal | Trade execution price | Must be greater than 0 |
| Quantity | Integer | Number of shares traded | Must be greater than 0 |
| Time Stamp | Date Time | Execution timestamp (UTC) | Must be valid UTC |
| Reported_Party | String | Reporting entity’s LEI | Must exist in LEI registry |

---

## 6. Framework Overview
The Equity Trade Data Quality Framework ensures that trade data is validated against schema, business, and regulatory rules before submission.

| Component | Function |
|------------|-----------|
| Data Ingestion | Reads data from trade systems or data lakes |
| Schema Validator | Ensures format and structure compliance |
| Business Validator | Applies logical trade and pricing rules |
| Regulator Validator | Cross-checks against MiFID II and FCA rules |
| Reporting Module | Generates compliance summary and reliability scores |
| Audit Logger | Stores validation metadata for traceability |

---

## 7. Folder Structure
