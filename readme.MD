Jenkins
Create Jenkins master, Jenkins agent EC2 instances. Update R53 records.
Install below plugins when you started Jenkins.

Plugins:

Pipeline stage view
Pipeline Utility Steps
AWS Credentials
AWS Steps
Rebuild
Ansi Color
SonarScanner
Restart Jenkins once plugins are installed

Manage Credentials:
We need to add ssh credentials for Jenkins to connect to agent. I am using ID as ssh-auth.
We need to add aws credentials for Jenkins to connect with AWS for deployments. I am using
aws-creds
aws-creds-prod
aws-creds-dev
Connect to SonarQube EC2 instance from EC2 connect in AWS console UI.
We need to get security token from my account in sonarqube.
We need to add Sonar credentials for Jenkins to connect with Sonar Server. I am using sonar-auth as ID.
Configure Master and Agent
Configure SonarScanner and SonarQube Server
Configure Jenkins Shared Libraries
Go to Manage Jenkins -> System
Find Global Trusted Pipeline Libraries section
Name as jenkins-shared-library, default version main and load implicitly
Location is https://github.com/daws-84s/jenkins-shared-library.git
Now Jenkins is ready to use.

EKS
Make sure roboshop namespace exist.
make sure EKS control plane allows Jenkins agent to connect on port 443 HTTPS.
SonarQube Quality Gates
🔴 Bugs What it means: Definite coding errors that will cause the program to behave incorrectly at runtime.

🟠 Code Smells What it means: Not actual errors, but poor coding practices that make code hard to maintain or read.

🟡 Coverage What it means: Percentage of code covered by automated tests (unit/integration tests).

🟣 Issues What it means: The total number of all problems detected = Bugs + Code Smells + Vulnerabilities.

🟢 Maintainability Rating What it means: A grade (A–E) showing how easy it is to maintain the code.

🔐 Security Rating What it means: Grade (A–E) for how secure the code is.

🛡️ Vulnerabilities What it means: Parts of the code that could be exploited by attackers.

Bugs = runtime errors. Code Smells = maintainability issues. Coverage = test percentage. Issues = all detected problems. Maintainability Rating = ease of maintaining code. Security Rating = safety from attacks. Vulnerabilities = exploitable weaknesses.

