---
layout: post
title:  "Practical example of a CI/CD workflow - what is CI and what is CD?"
date:   2023-01-17 11:00:00 +0000
categories: Code
---
Welcome to the world of CI/CD, the methodology that has changed software development. Adopted widely since the early 2010s, CI/CD streamlines the build, test, and deployment phases of software development, which are concepts that will be explained in this post, along with the benefits of CI/CD.

Here's an example of a basic CI/CD workflow for a generic code project:

1. CI: Code changes: A developer makes changes to the codebase, such as adding new features or fixing bugs. They then push the changes to a version control system like Git.

2. CI: Build and test: A CI tool like Travis CI detects the new code changes and automatically starts a build process. This process may include compiling the code, running automated tests, and generating artifacts like executable files or containers.

3. CI: Code quality checks: The CI tool may also run code quality checks, such as static code analysis, to ensure that the code adheres to certain standards and best practices.

4. CI: Feedback: If any of the build or test steps fail, the CI tool will notify the developer and provide feedback on what went wrong. If the build is successful, the developer will be notified as well.

5. CD: Deployment: Once the build is successful and all the tests passed, the CD tool will take over. This can include deploying the application to a test environment for further testing and validation, or deploying it to a production environment for users to access.

6. CD: Monitoring: After the application is deployed, the CD tool will monitor the application, tracking the performance and availability of the application. If there is any problem, the tool will notify the team and take actions to fix it.


For a simple Python project:

1. CI: Code changes: A developer makes changes to the Python codebase, such as adding new features or fixing bugs. They then create a new branch in the version control system like Git and push the changes to that branch.

2. CI: Build and test: A CI tool like Travis CI detects the new code changes in the branch and automatically starts a build process. This process may include installing dependencies specified in the project's requirements.txt file, running automated tests written in Python using a testing framework such as unittest or pytest.

3. CI: Code quality checks: The CI tool may also run code quality checks, such as linting using Flake8 or Pylint, to ensure that the code adheres to certain standards and best practices.

4. CI: Feedback: If any of the build or test steps fail, the CI tool will notify the developer through a email, slack or other means and provide feedback on what went wrong. If the build is successful, the developer will be notified as well.

5. CD: Deployment: Once the build is successful and all the tests passed, the CD tool will take over. This can include deploying the application to a test environment like a staging server, for further testing and validation, or deploying it to a production environment like AWS, GCP, Heroku or other cloud providers for users to access.

6. CD: Monitoring: After the application is deployed, the CD tool will monitor the application, tracking the performance and availability of the application. If there is any problem, the tool will notify the team and take actions to fix it like automatic rollback to previous version, or scaling up resources.
