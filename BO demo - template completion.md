| **Field**                          | **Value**                                                                                         |
|-----------------------------------|----------------------------------------------------------------------------------------------------|
| Step Name                         | Step 1.1: Receive Pooling Data from System B                                                       |
| Business Process                  | Stage 1: Trade Creation                                                                            |
| Description of Technical Function | System A receives batch files from System B, parses structured loan pool data, and stores results in internal tables for further processing. |
| Business Function / Purpose       | Ensures Business Unit A has accurate and timely loan pool data to support trade creation, compliance validation, and operational readiness. |
| Customers / Internal Users        | - Business Unit A analysts <br> - Trade operations team <br> - Compliance officers                |
| What Are Users Trying to Accomplish? | - Gain early access to complete and accurate loan pool data <br> - Ensure readiness for trade evaluation and compliance reviews |
| Target Outcomes (KPI)             | - Pool files available in System A within 30 minutes of receipt                                   |
| Definition or Formula (KPI)       | ```(Number of successfully ingested pool files / Number of expected files) × 100```               |
| Business Signals                  | - `Suggested:` *Percent of pool files ingested within SLA* <br> - `Suggested:` *Total loan records processed* <br> `Owner:` Product Owner |
| Process Signal                    | - `Suggested:` *Validation pass rate for required pool data fields (e.g., loan count, timestamps, field format)* <br> - `Suggested:` *File completeness confirmation logic executed* <br> `Owner:` Application Developer |
| System Signal                     | - `Suggested:` *System A file ingestion latency* <br> - `Suggested:` *System B queue interface uptime* <br> - `Suggested:` *Batch file processing success rate* <br> `Owner:` Platform SRE |
