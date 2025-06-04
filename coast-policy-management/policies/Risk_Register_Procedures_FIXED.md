# 🗂️ Risk Register Procedures
**Document Owner:** Risk Management Team
**Effective Date:** 2025-06-04
**Review Frequency:** Quarterly
**Version:** 2.0

Risk Register Procedures Document

## 1. Purpose
Purpose
This document outlines the procedures for maintaining and updating the Cybersecurity Risk Register (CSRR) as part of Coast Autonomous Systems' risk management framework. These procedures ensure that risks are consistently identified, assessed, documented, and monitored in alignment with NISTIR 8286A and the broader Enterprise Risk Management (ERM) strategy.

## 2. Scope
Scope
These procedures apply to all risk management activities concerning cybersecurity risks across all systems, networks, applications, and business units within Coast Autonomous Systems.

## 3. Risk Register Overview
Risk Register Overview
The Cybersecurity Risk Register (CSRR) is a tool for recording and tracking identified risks that could impact the confidentiality, integrity, or availability of Coast's systems and data. It captures essential information, including threat sources, vulnerabilities, potential impacts, likelihood, and risk responses.

## 4. Risk Identification Process
Risk Identification Process
Risk identification should follow a systematic approach to ensure all relevant risks are captured:
Asset Inventory and Valuation: Identify and document critical assets, including information systems, personnel, and physical infrastructure, that could be impacted by risks.
Threat Identification: Evaluate potential threat sources, including internal and external actors, natural disasters, and system vulnerabilities. Common sources include malicious insiders, cyberattacks, and technical failures.
Vulnerability Assessment: Identify weaknesses that could be exploited by the above threats.
Risk Scenario: Combine identified threats and vulnerabilities into risk scenarios that describe potential loss events (e.g., data breaches or system outages).
These risks are recorded in the CSRR using the Risk Description field.

Relevant NIST 800-53 Controls:
RA-3: Risk Assessment
RA-5: Vulnerability Scanning
CA-7: Continuous Monitoring

## 5. Risk Register Template
Risk Register Template
Each entry in the risk register should follow the format below:

| Field            | Description                                                  |
|------------------|--------------------------------------------------------------|
| Risk ID          | Unique identifier for each risk                              |
| Risk Description | Description of the risk scenario (threat, vulnerability, impact) |
| Risk Category    | Category of the risk (e.g., financial, operational, regulatory) |
| Asset Impacted   | The asset affected by the risk                               |
| Likelihood       | The estimated probability of the risk occurring              |
| Impact           | The potential severity of the risk's impact                  |
| Risk Exposure    | Combination of likelihood and impact                         |
| Risk Status      | Current status (e.g., active, mitigated, transferred)        |
| Risk Response    | Planned or implemented mitigation strategies                 |
| Risk Owner       | The person or team responsible for managing the risk         |

Relevant NIST 800-53 Controls:
RA-2: Security Categorization
RA-9: Risk Management Strategy

## 6. Risk Detail Records (RDR)
Risk Detail Records (RDR)
For risks that require further analysis, a Risk Detail Record (RDR) should be maintained. The RDR contains additional data, including:
Historical data related to the risk.
Detailed risk analysis (e.g., quantitative risk assessment).
Information about risk ownership and accountability.
Past risk responses and their outcomes.
The RDR is linked to each entry in the CSRR to provide more granular details when needed.

Relevant NIST 800-53 Controls:
RA-3: Risk Assessment
PM-9: Risk Management Process
RA-7: Risk Response

## 7. Risk Categorization
Risk Categorization
Risks should be categorized based on their impact and type. Examples of categories include:
Operational Risks: Related to system outages, business interruptions, or human error.
Regulatory Risks: Linked to compliance failures or legal exposures.
Financial Risks: Potential financial loss due to cyberattacks or system breaches.
Reputational Risks: Damage to Coast’s brand or customer trust.

Relevant NIST 800-53 Controls:
RA-2: Security Categorization
SA-14: Criticality Analysis
PM-4: Risk Framing

## 8. Risk Analysis
Risk Analysis
Once risks are identified, the likelihood and impact should be estimated using qualitative or quantitative methods:
Likelihood: Assign a probability to each risk based on historical data and expert judgment.
Impact: Evaluate the potential consequences, considering financial, operational, and reputational damage.
Risk Exposure: Calculated by multiplying likelihood and impact, guiding the prioritization of risks.

Relevant NIST 800-53 Controls:
RA-4: Risk Assessment Methodology
RA-5: Vulnerability Scanning
CA-7: Continuous Monitoring

## 9. Risk Response
Risk Response
For each risk, one or more of the following responses should be documented:
Mitigation: Implement controls to reduce the likelihood or impact of the risk.
Transfer: Shift the risk to a third party (e.g., through insurance or outsourcing).
Acceptance: Acknowledge the risk and take no further action, if within risk tolerance.
Avoidance: Eliminate the risk by discontinuing the risky activity or process.
The response chosen will be recorded in the Risk Response field of the CSRR, along with actions taken.

Relevant NIST 800-53 Controls:
RA-7: Risk Response
SA-9: External System Services
PM-9: Risk Management Process


## 10. Continuous Monitoring and Review
Continuous Monitoring and Review
The CSRR will be reviewed quarterly, and as new risks are identified or conditions change, updates will be made to the risk entries and associated RDRs. Continuous monitoring ensures that risk exposures are reassessed and new risks are promptly added to the register.
Relevant NIST 800-53 Controls:
CA-7: Continuous Monitoring
PM-4: Risk Framing
RA-9: Risk Management Strategy


## 🔒 NIST 800-53 Rev. 5 Control Mapping


| Control | Title                          | Relevance                                               |
|---------|--------------------------------|----------------------------------------------------------|
| RA-2    | Security Categorization         | Risk type and impact classification                     |
| RA-3    | Risk Assessment                 | Core of the risk identification and analysis processes  |
| RA-4    | Risk Assessment Methodology     | Risk evaluation through likelihood and impact scoring   |
| RA-5    | Vulnerability Scanning          | Input into risk identification                          |
| RA-7    | Risk Response                   | Actions to mitigate, accept, transfer, or avoid risks   |
| RA-9    | Risk Management Strategy        | Strategy and structure for ongoing risk activities      |
| CA-7    | Continuous Monitoring           | Risk review and update cadence                          |
| PM-4    | Risk Framing                    | Organizational context and priorities for risk handling |
| PM-9    | Risk Management Process         | Standard procedures for documenting and reviewing risks |
| SA-9    | External System Services        | Risk transfer considerations through third parties      |
| SA-14   | Criticality Analysis            | Helps classify assets and prioritize risk               |


## 📜 Revision History


| Version | Date       | Author               | Description                   |
|---------|------------|----------------------|-------------------------------|
| 2.0     | 2025-06-04 | Risk Management Team | Updated procedures and format |
