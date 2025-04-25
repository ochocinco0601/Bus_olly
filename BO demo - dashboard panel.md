┌────────────────────────────────────────────────────────────────────────────┐
│      DASHBOARD PANEL — Step 1.1: Receive Pooling Data from System B        │
├────────────────────────────────────────────────────────────────────────────┤
│                                                                            │
│  🧭 Purpose: Ensure timely and complete ingestion of pool data from         │
│  System B into System A to support trade creation and compliance reviews   │
│                                                                            │
│  📌 Used by: Business Unit A Analysts, Trade Operations, Compliance         │
│                                                                            │
│  📈 BUSINESS SIGNALS                                                       │
│  - Percent of Pool Files Ingested Within SLA: 98% ✓  (`Owner:` Product Owner)       │
│  - Total Loan Records Processed: 12,340 ✓  (`Owner:` Product Owner)                 │
│                                                                            │
│  ⚙ PERFORMANCE RELIABILITY SIGNALS                                         │
│  🟨 Process Signals                                                        │
│  - Validation Pass Rate (Required Fields): 99% ✓  (`Owner:` Application Developer)  │
│  - File Completeness Check Executed: 100% ✓  (`Owner:` Application Developer)      │
│                                                                            │
│  🟧 System Signals                                                         │
│  - System A Ingestion Job Latency (p95): 1800ms ✓  (`Owner:` Platform SRE)        │
│  - System B Delivery Job Success Rate: 100% ✓  (`Owner:` Platform SRE)            │
│  - Batch File Processing Error Count: 0 ✓  (`Owner:` Platform SRE)                │
│                                                                            │
│  🚨 RECENT ALERTS                                                          │
│  - [INFO] All files processed within SLA                                  │
│  - [INFO] No ingestion or validation errors in the past 24 hours          │
│                                                                            │
│  🔍 NEXT STEPS                                                             │
│  • Continue monitoring latency trends on ingestion jobs                   │
│  • Investigate any future validation drops below 98%                      │
│  • Validate completeness logic daily to avoid downstream readiness issues │
└────────────────────────────────────────────────────────────────────────────┘
