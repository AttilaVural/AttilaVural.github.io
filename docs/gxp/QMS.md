# Keeping in Compliance - QMS
Federal regulation recommend pharmaceutiacal companies to adopt a QMS system, 
which is a high level strategy defined by upper management, that describes how GMP-related 
activites, and general business related activites, should be carried out and prioritized to achieve the desired level of product quality.
They are usually built around the ISO 9001 and ISO 13485 standards.

``` mermaid
	graph LR
		subgraph TOP [" "];
					G[Regulatory requirements];
						G --- H[Processes];
						G --- I[Procedures];
						G --- M[Change Management];
						G --- L[Training of employees];
						G --- N[Deviation Management];
						G --- O[Change Management];
						G --- P[Configuration Management];
						G --- Q[IT Risk Assessment];
					
			NOTE["Implementation specifics <br> are defined in each <br> company's QMS"];
		end
	class NOTE dashedNote
	class TOP transparant
	classDef dashedNote fill:#00000000,text-align:left,stroke-dasharray:5,font-weight:bold;
	classDef transparant fill:#00000000,stroke:#00000000;
```