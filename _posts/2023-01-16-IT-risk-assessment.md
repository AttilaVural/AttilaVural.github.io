---
layout: post
title:  "Assessing the Security and Compliance of GxP IT systems using a Risk Assessment Tool"
date:   2023-01-15 15:00:00 +0000
categories: Misc
mermaid: true
---
## Using the Risk Assessment tool for planning validation activities
### Determine relevant IT risk controls to test during validation of an IT system after implenting changes
1. Determine which of the listed generic IT URS requirement are likely to be impacted by the change.
2. From these URS requirements, selected the corresponding IT risk controls, which have been implemented for the current system, and which might be affected by the planned activities.
3. Use your knowledge of the IT system to formulate the test-steps needed to ensure that these risk controls work as intended.



<div class="mermaid">
  graph TD
      A([Assess Gross Risk]) 
        A--> B{What phase is <br> the project in?}
      B -->|Design <br> phase| D{...}
      B -->|Already Built <br> system| E{Are risks stills present?}
      E -->|No| F([The system is already fully defined <br> and implemented, and there has <br> not been found any need for <br> implementing additional risk controls to <br> mitigate security gaps or potentially <br> failing controls.])
</div>

