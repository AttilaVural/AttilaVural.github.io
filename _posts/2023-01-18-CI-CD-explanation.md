---
layout: post
title:  "Practical example of a CI/CD workflow - what is CI and what is CD?"
date:   2023-01-17 11:00:00 +0000
categories: jekyll update
---
Here's an example of a basic CI/CD workflow:

CI: Code changes: A developer makes changes to the codebase, such as adding new features or fixing bugs. They then push the changes to a version control system like Git.

CI: Build and test: A CI tool like Travis CI detects the new code changes and automatically starts a build process. This process may include compiling the code, running automated tests, and generating artifacts like executable files or containers.

CI: Code quality checks: The CI tool may also run code quality checks, such as static code analysis, to ensure that the code adheres to certain standards and best practices.

CI: Feedback: If any of the build or test steps fail, the CI tool will notify the developer and provide feedback on what went wrong. If the build is successful, the developer will be notified as well.

CD: Deployment: Once the build is successful and all the tests passed, the CD tool will take over. This can include deploying the application to a test environment for further testing and validation, or deploying it to a production environment for users to access.

CD: Monitoring: After the application is deployed, the CD tool will monitor the application, tracking the performance and availability of the application. If there is any problem, the tool will notify the team and take actions to fix it.
