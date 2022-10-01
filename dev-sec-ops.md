# DevSecOps

## The concept of DevSecOps

DevSecOps or DevOps security is about introducing security earlier in the life cycle of application development (a.k.a shift-left), thus minimizing the impact of vulnerabilities and bringing security closer to development team.

## Why

By embracing shift-left mentality, DevSecOps encourages organizations to bridge the gap that often exists between development and security teams to the point where many of the security processes are automated and are effectively handled by the development team.

## DevSecOps Practices

This section covers different tools, frameworks and resources allowing introduction of DevSecOps best practices to your project at early stages of development.

_Topics to be covered (Work in progress):_

1. [Container Dependencies Scanning](#applying-dependency-and-container-scanning) - search for vulnerabilities in container operating systems, language packages and application dependencies.
1. Credential Scanning automatically inspecting a project to ensure that no secrets are included in the project's source code.
1. Secrets Rotation - automated process by which the secret, used by the application, is refreshed and replaced by a new secret.
1. Static Code Analysis - analyze source code or compiled versions of code to help find security flaws.
1. Automated Penetration Testing - a simulated attack against your application to check for exploitable vulnerabilities.

---

## Dependency and Container Scanning

Dependency and Container scanning is performed in order to search for vulnerabilities in operating systems, language and application packages.

### Why Dependency and Container Scanning

Container images are standard application delivery format in cloud-native environments.
Having a broad selection of images from the community, we often choose a community base image, and then add packages that we need to it, which might also come from community sources.
Those arbitrary dependencies might introduce vulnerabilities to our image and application.

### Applying Dependency and Container Scanning

Images that contain software with security vulnerabilities become exploitable at runtime. When building an image in your CI pipeline, image scanning must be a requirement for a build to pass. Images that did not pass scanning should never be pushed to your production-accessible container registry.

Dependency and Container scanning best practices:

1. Base Image - if your image is built on top of a third-party base image, validate the following:
   - The image comes from a well-known company or open-source group.
   - It is hosted on a reputable registry.
   - The Dockerfile is available, and check for dependencies installed in it.
   - The image is frequently updated - old images might not contain the latest security updates.
1. Remove Non-Essential Software - Start with a minimal base image and install only the tools, libraries and configuration files that are required by your application.
Avoid installing the following tools or remove them if present:
    - Network tools and clients: e.g., wget, curl, netcat, ssh.
    - Shells: e.g. sh, bash. Note that removing shells also prevents the use of shell scripts at runtime. Instead, use an executable when possible.
    - Compilers and debuggers. These should be used only in build and development containers, but never in production containers.
1. Container images should be immutable - download and include all the required dependencies during the image build.
1. Scan for vulnerabilities in software dependencies -  today there is likely no software project without some form of external libraries, dependencies or open source.
While it allows the development team to focus on their application code, the dependency brings forth an expected downside where the security posture of the real application is now resting on it.
To detect vulnerabilities contained within a project’s dependencies use container scanning tools which as part of their analysis scan the software dependencies (see "Dependency and Container Scanning Frameworks and Tools").

### Dependency and Container Scanning Frameworks and Tools

1. [Trivy](https://github.com/aquasecurity/trivy) - a simple and comprehensive vulnerability scanner for containers (doesn't support Windows containers)
1. [Aqua](https://www.aquasec.com/solutions/azure-container-security/) - dependency and container scanning for applications running on AKS, ACI and Windows Containers. Has an integration with AzDO pipelines.
1. [Dependency-Check Plugin for SonarQube](https://github.com/dependency-check/dependency-check-sonar-plugin) - OnPrem dependency scanning
1. [WhiteSource](https://www.whitesourcesoftware.com/open-source-security-lp/?utm_origin=ad&utm_from=Adwords&utm_pcampaign=fs.brand.rotw.search&utm_gen=Searched%20Term:whitesource&gclid=Cj0KCQjw4cOEBhDMARIsAA3XDRg55QPm_0DkVaDxJnVE7bX6s2hBCKa0QfezPZG1p-JhaxBCG8TgozsaAgIWEALw_wcB) - Open Source Scanning Software

### Conclusion

Containers should be used carefully. Install the minimal requirements needed for your application, be aware of the software dependencies your application is using and make sure to maintain it over time by using container and dependencies scanning tools.
