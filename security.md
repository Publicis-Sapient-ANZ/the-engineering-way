# Security

Developers working on PS Australia projects should adhere to industry-recommended standard practices for secure design and implementation of code. For the purposes of our customers, this means our engineers should as a minimum understand the [OWASP Top 10 Web Application Security Risks](https://owasp.org/www-project-top-ten/), as well as how to mitigate as many of them as possible, using the resources below.

**If you are looking for a fast way to get started** evaluating your application or design, check out the "Secure Coding Practices Quick Reference" document below, which contains an itemized checklist of high-level concepts you can validate are being done properly. This checklist covers many common errors associated with the OWASP Top 10 list linked above, and should be the minimum amount of effort being put into security.

## Quick References

- [Secure Coding Practices Quick Reference](https://owasp.org/www-pdf-archive/OWASP_SCP_Quick_Reference_Guide_v2.pdf)
- [Web Application Security Quick Reference](https://owasp.org/www-pdf-archive//OWASP_Web_Application_Security_Quick_Reference_Guide_0.3.pdf)
- [Security Mindset/Creating a Security Program Quick Start](https://github.com/OWASP/Quick-Start-Guide/blob/master/OWASP%20Quick%20Start%20Guide.pdf?raw=true)
- [Automated Secret Detection](#secret-detection)

## DevSecOps

Introduce security to your project at early stages. The [DevSecOps section](dev-sec-ops.md) covers security practices, automation, tools and frameworks as part of the application CI.

## OWASP Cheat Sheets

> Note: OWASP is considered to be the gold-standard in computer security information. OWASP maintains an extensive series of cheat sheets which cover all the OWASP Top 10 and more. Below, many of the more relevant cheat sheets have been summarized. To view all the cheat sheets, check out their [Cheat Sheet Index](https://github.com/OWASP/CheatSheetSeries/blob/master/Index.md).

- [Access Control Basics](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Access_Control_Cheat_Sheet.md)
- [Attack Surface Analysis](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Attack_Surface_Analysis_Cheat_Sheet.md)
- [Content Security Policy (CSP)](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Content_Security_Policy_Cheat_Sheet.md)
- [Cross-Site Request Forgery (CSRF) Prevention](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.md)
- [Cross-Site Scripting (XSS) Prevention](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.md)
- [Cryptographic Storage](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Cryptographic_Storage_Cheat_Sheet.md)
- [Deserialization](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Deserialization_Cheat_Sheet.md)
- [Docker/Kubernetes (k8s) Security](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Docker_Security_Cheat_Sheet.md)
- [Input Validation](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Input_Validation_Cheat_Sheet.md)
- [Key Management](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Key_Management_Cheat_Sheet.md)
- [OS Command Injection Defense](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/OS_Command_Injection_Defense_Cheat_Sheet.md)
- [Query Parameterization Examples](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Query_Parameterization_Cheat_Sheet.md)
- [Server-Side Request Forgery Prevention](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.md)
- [SQL Injection Prevention](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.md)
- [Unvalidated Redirects and Forwards](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.md)
- [Web Service Security](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Web_Service_Security_Cheat_Sheet.md)
- [XML Security](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/XML_Security_Cheat_Sheet.md)

## Recommended Tools

Check out the list of tools to help enable security in your projects.

> **Note:** Although some tools are agnostic, the below list is geared towards Cloud Native security, with a focus on Kubernetes.

- Vulnerability Scanning

  - [SonarCloud](https://sonarcloud.io/)
    - Integrates with Azure Devops with the click of a button.
  - [Snyk](https://github.com/snyk/snyk)
  - [Trivy](https://github.com/aquasecurity/trivy)
  - [Cloudsploit](https://github.com/aquasecurity/cloudsploit)
  - [Anchore](https://github.com/anchore/anchore-engine)
  - [Other tools from OWASP](https://owasp.org/www-community/Vulnerability_Scanning_Tools)
  - [See why you should check for vulnerabilities at all layers of the stack](https://sysdig.com/blog/image-scanning-best-practices/), as well as a couple of other useful tips to reduce surface area for attacks.

- Runtime Security

  - [Falco](https://github.com/falcosecurity/falco)
  - [Tracee](https://github.com/aquasecurity/tracee)
  - [Kubelinter](https://github.com/stackrox/kube-linter)
    - May not fully qualify as runtime security, but helps ensure you're enabling best practices.

- Binary Authorization

  Binary authorization can happen both at the docker registry layer, and runtime (ie: via a K8s admission controller).
  The authorization check ensures that the image is signed by a trusted authority. This can occur for both (pre-approved) 3rd party images,
  and internal images. Taking this a step further the signing should occur _only_ on images where all code has been reviewed and approved.
  Binary authorization can both reduce the impact of damage from a compromised hosting environment, and the damage from malicious insiders.

  - [Harbor](https://github.com/goharbor/harbor/)
    - [Operator available](https://github.com/goharbor/harbor-operator)
  - [Portieris](https://github.com/IBM/portieris)
  - [Notary](https://github.com/theupdateframework/notary)
    - Note harbor leverages notary internally.
  - [TUF](https://github.com/theupdateframework/tuf)

- Other K8s Security

  - [OPA](https://github.com/open-policy-agent/opa), [Gatekeeper](https://github.com/open-policy-agent/gatekeeper), and the [Gatekeeper Library](https://github.com/open-policy-agent/gatekeeper-library/tree/master/library)
  - [cert-manager](https://github.com/jetstack/cert-manager) for easy certificate provisioning and automatic rotation.
  - [Quickly enable mTLS between your microservices with Linkerd](https://linkerd.io/2/features/automatic-mtls/).

## Secret Detection

It is important to ensure that secrets don't make it in to the code base and compromise the security of our application data. The best way of doing so is by introducing a simple and easy way to detect secrets during its development, and gate for secrets in your CI/CD pipelines.
This section describes how we can use the open-source secrets detection framework [Yelp Detect-Secrets](https://github.com/Yelp/detect-secrets), to accomplish this together with two tools from the Detect-Secrets framework created by the CSE Engineering Fundamentals and Security group.
The Yelp Detect-Secrets tool utilizes a Shannon Entropy model to detect secrets in code bases and prevents new secrets from being entered.

### Detect Secrets Pre-Commit Hook

The Detect-Secrets pre-commit hook is a tool that keeps secrets from being entering the codebase at one of the earliest stages of development.
This tool will run a detect-secrets scan right before a Git commit occurs and if any findings occur, then mitigation can occur before any history of the secret is generated in Git history.
Using the Detect Secrets Pre-Commit approach developers can ensure they don't accidentally commit secrets at the earliest point in the development cycle but at a project level it requires all developers to adopt this approach to provide protection.

### Configuration for Environment

Below are two ways of setting up your environment depending on your use case.

- [Pre-Commit Hook within Existing Repo](https://github.com/wbreza/pre-commit-hooks/blob/main/detect-secrets/README.md)
  - Simple install script bootstraps existing repos with pre-commit hooks and helper scripts to help manage the secret detection lifecycle
- [Pre-Commit Hook with New Repo Template](https://github.com/wbreza/baseline-security-seed/blob/main/SECURITY.md)
  - Contains all of the above plus out of the box support for dev containers using the Github universal dev container image.
  - Also includes a GitHub workflow to additionally perform secret detection within pull requests


### Additional Reading

- [Yelp/detect-secrets: An enterprise friendly way of detecting and preventing secrets in code.](https://github.com/Yelp/detect-secrets)
