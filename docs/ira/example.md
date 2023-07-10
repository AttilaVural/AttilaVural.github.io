# IT Risk Assessment - example

## Generic freeze dryer


=== "System"
	| IT solution details | Value | Comments |
	| --- | --- | --- |
	| Type of IT | Computerized system | Computer system that controls a GxP process. |
	| IT solution name and version | Freeze dryer 32 | Freeze dryer located in building [redacted]. Freeze drying liquid medication is to remove water from the product, making it more stable and easier to store and transport. |
	| Scope of risk assessment | SCADA & SQL Servers, HMI clients, PLCs | Necessary IT infrastructure is covered in seperate risk assessment. |

=== "Gross impact"
	| Breach type | Impact area | Rationale | Worst-case severity before mitigating controls | Rationale |
	|-------------|---------|-----------|-----------|-----------|
	| Confidentiality breach | Regulatory compliance | No business criticality with the freeze dryers under a confidentiality breach. Equipment does not contain any sensitive or confidential data. | Minor | FDA 483 due to minor findings or equivalent from other regulatory bodies. | 
	| Integrity breach | Product quality | Corrupted or deleted data could have an impact on product quality. | Minor | Dissatisfactory product quality registered during inspection. |
	| Availability breach | Financial | There is a possibility that production will be put on standby during trouble. | 50 mUSD - 150 mUSD | In case the recovery plan is invoked, an RTO of 7 days is expected, along with reduced capacity during this period. |```

=== "Gross likelyhood"
	.............................
	
=== "Suggested risk controls"
	.............................
	
=== "Risk overview"
	.............................