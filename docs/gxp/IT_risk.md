<!-- ## Assessing IT risk based standard URS requirements -->
## Regulatory foundation

Section 16 in [EU GMP Annex 11](index.md) states that computerized systems must be risk assessed to ensure a stable business process:

_For the ==availability of computerised systems== supporting critical processes, provisions should 
be made to ensure continuity of support for those processes in the event of a system 
breakdown (e.g. a manual or alternative system). The time required to bring the alternative 
arrangements into use ==should be based on risk== and appropriate for a particular system and the 
business process it supports. These arrangements should be adequately documented and tested_

Federal agencies mandates these assessments, as a sudden production stop could mean a drug shortage, thereby endangering lives.

<!--
## Assessing Gross Risk

## Using the Risk Assessment tool for planning validation activities
### Determine relevant IT risk controls to test during validation of an IT system after implenting changes
1. Determine which of the listed generic IT URS requirement are likely to be impacted by the change.
2. From these URS requirements, selected the corresponding IT risk controls, which have been implemented for the current system, and which might be affected by the planned activities.
3. Use your knowledge of the IT system to formulate the test-steps needed to ensure that these risk controls work as intended.

```mermaid
graph TD
	A([Assess Gross Risk using FAIR]);
	A--> B{What phase is <br> the project in?};
	B -->|Design <br> phase| D{...};
	B -->|Already built <br> system| E{Are risks <br>present?};
	E -->|No| F(Are there any potentially <br>failing important controls?);
	F -->|No| I([Gross Risk = Net Risk])
	F -->|Yes| G
	E -->|Yes| G[Suggest appropriate <br>Mitigating Controls]
	G --> H(["Net Risk = <br>Gross Risk + <br>Mitigating Controls"])
	
```
-->