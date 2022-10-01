# Non-Functional Requirements Capture

## Goals

In software engineering projects, important characteristics of the system providing for necessary e.g., testability, reliability, scalability, observability, securability, manageability are best considered as first-class citizens in the requirements gathering process.
By defining these non-functional requirements in detail early in the engagement, they can be properly evaluated when the cost of their impact on subsequent design decisions is comparatively low.

To support the process of capturing a project's _comprehensive_ non-functional requirements, this document offers a taxonomy for non-functional requirements and provides a framework for their identification, exploration, assignment of customer stakeholders, and eventual codification into formal engineering requirements as input to subsequent solution design.

---

## Areas of Investigation

### [Enterprise Security](security.md)

- Privacy
  - PII
  - HIPAA
- Encryption
- Data mobility
  - at rest
  - in motion
  - in process/memory
- Key Management
  - responsibility
    - platform
    - BYOK
    - CMK
- INFOSEC regulations/standards
  - e.g., FIPS-140-2
    - Level 2
    - Level 3
  - ISO 27000 series
  - NIST
  - Other
- Network security
  - Physical/Logical traffic boundaries/flow topology
    - Cloud <-- --> On-prem
    - Public <-- --> Cloud
    - VNET
    - PIP
    - Firewalls
    - VPN
    - ExpressRoute
      - Topology
      - Security
  - Certificates
    - Issuer
      - CA
      - Self-signed
      - Rotation/expiry
- INFOSEC Incident Response
  - Process
  - People
  - Responsibilities
  - Systems
  - Legal/Regulatory/Compliance

### Enterprise AuthN/AuthZ

- Users
- Services
- Authorities/directories
- Mechanisms/handshakes
  - Active Directory
  - SAML
  - OAuth
  - Other
- RBAC
  - Perms inheritance model

### [Enterprise Monitoring/Operations](observability.md)

- Logging
  - Operations
  - Reporting
  - Audit
- Monitoring
  - Diagnostics/Alerts
  - Operations
- HA/DR
  - Redundancy
  - Recovery/Mitigation
- Practices
  - Principle of least-privilege
  - Principle of separation-of-responsibilities
- Service Level Agreements
  - Business Level metrics (customer transactions, order volumes, etc)
  - Technology centric metrics (uptime, RTO, RPO, MTTR etc) 

### Other standard Enterprise technologies/practices

- Developer ecosystem
  - Platform/OS
    - Hardened
    - Approved base images
    - Image repository
  - Tools, languages
    - Approval process
  - Code repositories
    - Secrets management patterns
      - Env var
      - Config file(s)
      - Secrets retrieval API
  - Package manager source(s)
    - Private
    - Public
    - Approved/Trusted
  - CI/CD
  - Artifact repositories

### Production ecosystem

- Platform/OS
  - Hardened
  - Approved base images
  - Image repository
- Deployment longevity/volatility
  - Automation
  - Reproducibility
    - IaC
    - Scripting
    - Other

### Other areas/topics not addressed above (requires customer input to comprehensively enumerate)

For example: In banking customers there maybe technical risk and compliance requirements to explore. Or 3rd party SLAs to meet, or Batch processing timings to operate within etc.  

---

## Investigation Process

1. Identify/brainstorm likely areas/topics requiring further investigation/definition
1. Identify customer stakeholder(s) responsible for each identified area/topic
1. Schedule debrief/requirements definition session(s) with each stakeholder
   - as necessary to achieve sufficient understanding of the probable impact of each requirement to the project
   - both current/initial milestone and long-term/road map
1. Document requirements/dependencies identified and related design constraints
1. Evaluate current/near-term planned milestone(s) through the lens of the identified requirements/constraints
   - Categorize each requirement as affecting immediate/near-term milestone(s) or as applicable instead to the longer-term road map/subsequent milestones
1. Adapt plans for current/near-term milestone(s) to accommodate immediate/near-term-categorized requirements

