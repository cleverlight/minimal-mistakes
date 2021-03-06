---
layout: single
title: Web service review and Cloud audit
description: Beyond the code, there's so much that needs to be thought about when launching and running a production-grade, scalable and extensible app or web service.  Let's get specific!
tags: front services tech devops
toc: true
preview:
    parentheses: "(Checklist)"
header:
    overlay_image: /assets/images/auditsky_07013_1920x.jpg
    small_image: /assets/images/auditsky_07013_640x.jpg
permalink: /tech/2018/web-service-review-and-cloud-audit/
---

Every audit is about deeply understanding a technology platform and the people who are responsible for it.
That process is as unique as the project itself, but we tend to ask a standard set of questions to ensure that nothing gets overlooked.

## Drawing data out
### Log capture
* What does your log pipeline look like? (e.g. Fluentd, Logstash, Elasticsearch)
* How long are logs retained for?
* What's the log latency from capture to analysis?
* What data is redacted from the logs and where in the pipeline?
* What container-level, host-level or environment-level data is logged?

### Application log analysis
* What technologies do you use to analyse logs? (e.g. Kibana) 
* Who supports the application?
* Are the developers involved and if so at what 'line'?
* Who has access to application logs (in different environments)?
* What IDs are related log entries joined by?
* Who is responsible for the logs, their readability, utility and insights?

### Security log analysis
* How are attacks detected?
* Once detected, how is an attack understood?
* How are threat actors identified and blocked?
* Do you receive or subscribe to any threat analysis services?  If so, how do you act on that information?
* Do you conduct any pattern analysis on logs to identify new threats?
* Which (IdP) systems on your network conduct user authentication (validating who they are) and authorisation (giving them permission to do things)?
* Are all access attempts on IdP systems logged?
* Who is responsible for reviewing, categorising and (where appropriate) verifying failed access attempts?

### APM
* How do you profile application performance?
* What technologies do you use for APM? (e.g. Stackify, Dynatrace)
* Where are the known bottlenecks in your application?
* When do you conduct optimisation?
 
## Managing code
### Source control
* What source control do you use? (e.g. GitHub)
* What's your branching strategy?
* Where are different branches deployed?
* How are production branches identified?
* What systems refer to your source control system?
  
### Continuous Integration
* How does the build process work?
* What software orchestrates the build process? (e.g. Jenkins)
* What artifacts are produced by the build?
* How are tested changes merged into the codebase?
* Is there a static/dynamic code review performed on each merge?
* Are any code quality tests run as part of a merge?

### Configuration management
* What tools are used to handle configuration management? (e.g. Puppet, Ansible, Chef)
* What configuration logs are kept?
* Can administrators directly access production systems?
* How much manual intervention is required during environment provisioning?

### Artifact management (e.g. Artifactory)
* How are static assets handled?
* How is the code versioned?
* How are tags/identifiers/names used to connect artifacts with source versions?
* Where are version:environment deployment logs kept? 

## Deployments and environments
### Environment management
* What environments do you maintain for the product/project?
* What is the path to live through those environments?
* Are there any shared environments used by multiple projects or their administration?
* How are new environments provisioned?

### Continuous Deployment (e.g. Jenkins)
* How are builds deployed to production?
* Does the deployment process vary for dev, test, staging or production?
* What deployment strategies do you use into production? (e.g. Rolling/Canary/Recreate)
* How do you handle breaking changes? (e.g. a breaking schema update on the database)

### Container hosting (e.g. Docker)
* Do you use containers in dev?
* Do you use containers in production?
* Upon what image do you base your containers?
* How are containers built?

### Container orchestration
* How do you orchestrate your containers in production? (e.g. Kubernetes, Docker Swarm)
* What degree of control do you have over the orchestration layer?
* How do you handle platform updates?
* How is access controlled to the platform?

## Machines and services
### Subscribed service provisioning (e.g. CloudFormation for AWS RDS/Lambda/DynamoDB)
* What subscription-based services do you use in favour of building/running/managing yourself?
* To what extent are you dependent upon those services?
* What SLAs do you have in place with those vendors?
* How do you manage the risks associated with vendor lock-in?

### Machine provisioning
* What tools do you use for machine provisioning? (e.g. Terraform)
* Is that provisioning idempotent (reliably repeatable as exactly once) or are there uncontrolled environmental/human influences?
* How is your infrastructure versioned?
* How is provisioning state handled? (e.g. local, S3 bucket, other - Atlas)

### Patch management
* For self-managed hosts, how are operating systems and application servers patched?
* How do you stage those patches before releasing into production?
* To what extent are you exposed to upstream changes? (e.g. NPM left-pad chaos)
* If using a gold OS build, how are older systems up-levelled to the latest gold build?

### Secure base operating system
* For self-managed hosts, where do you source the base operating system image?
* What hardening do you undertake of the image?
* What additional tools do you install on all hosts?
* Do you maintain your own gold build, or if not how do you standardise at the OS level?

### Secret management
* What information is classified as secret?
* Where are secrets stored?
* What technology is used to store and protect secrets? (e.g. Vault or KMS)
* How are limited-lifetime secrets (e.g. certificates) rotated?
* Who is allowed access to the secret management system?
* How are machines granted access to secrets?
* Where else are secrets persisted and in what state (encoded/encrypted)?

### Off-cloud access and LAN integration (e.g. AWS DirectConnect)
* How do engineers access your production systems?
* What separation exists between your local area network (LAN) and the production network?
* What kind of external access is available to your staff?  How is that restricted?

## People and processes
### \[Maintenance\] User management
* Who has access to your production systems?
* Under what situations is access granted?
* How is access controlled?
* How are maintenance users separated from application users?
* Can administrators masquerade as application users or perform operations as-if them?

### Architecture
* Is the system broken into services and if so, at what granularity? (e.g. Monolith, microservices, nano-services)
* When segmenting a system
* Is the system architecture horizontally scalable?
* How do you decouple your services?
* What jobs/tasks/operations are handled asynchronously?
* How do you handle sync-async transitions when users (synchronous web requests) encounter those asynchronous tasks?
* How do you assess good vs bad architecture?

### Development methodology
* How does are requirements identified and managed?
* Who performs business analysis and what level of domain knowledge do they have?
* How is change managed, who originates a 'change' and tracks it?
* What does knowledge management mean to you team?
* Ticket management
  
### Incident management
* How are incidents managed?
* Do you perform retrospective analysis (or RCA) on incidents?
* Do you rate the severity of each incident?
* What response times do you aim to hit for an incident?  How do these vary by severity?
* What is your service Recovery Point Object (RPO, how old can the data be from the backups)?
* What is your service Recovery Time Object (RTO, how quickly can you recover from a disaster)?
* Is your incident management process linked to your Security Log Analysis and Data Integrity Management/data breach detection processes?

### Governance
* How empowered are your architects, developers, testers and other engineers to make technical decisions?
* What kind of governance process exists to manage technical decision making?
* How are decisions evaluated, logged and disseminated?
* Who is responsible for assessing the business impact of technical decisions?

## General Data Protection Regulation (GDPR)
### Storage
* Where and how is your data stored?
* If you store backups, where and how are they stored?
* How is data encrypted in-transit and at-rest?

### Data privacy and consent
* What types of data are being captured and which of these is kept?
* How do you identify personal data?
* Have you included in your data management processes all employee data too?
* How long is the personal data retained for?
* Do you maintain a clear set of terms and conditions that cover data privacy?  How often is this reviewed?
* Do you have a log of when each user accepted those terms, by version?
* What provision do you make for users requesting access to their data?
* What provision do you make for users to request the removal of their data?
* Do you follow privacy-by-design, and if so how does that relate to your Governance and Software Architecture processes?
* Do you have data on children?  How do you verify their age and get guardian approval?

### Data controls
* Who is authorised to view/edit/delete the data?
* What physical safeguards exist to limit that access to those who are authorised?
* What virtual/digital safeguards exist to limit that access to authorised users?
* Who is the Data Controller and the Data Protection Officer?
* Who is responsible in the organisation for GDPR regulations and compliance?
* Can you provide a document to clearly explain all data flows and touch points with your systems or staff?

### Outsourcing
* Do you maintain a current list of the outsourcers and partner who collect, manage, process or in some other way have access to data on your behalf?
* Does this list include all the Cloud services your staff use on a daily basis?
* Do you have a clear understanding of their policies and procedures for handling data?
* How do you handle shadow IT (services that are used without being run/managed by your central IT function)?
* How do you manage staff training around your IT systems and their regulatory or compliance obligations?

### Breaches
* What mechanisms do you have in place to detect data breaches?
* Do you have a communication plan in place to enact in the event of a data breach?

## Payment Card Industry Data Security Standard (PCI DSS)
### Scope
* Does the service interact in any way with card payment processing?
    * Does it control how consumers are redirected to a validated third-party service provider?
* Have you reviewed the relevant Self-Assessment Questionnaire (SAQ) for PCI compliance?
* Do you already know which SAQ classification you fall into:
    + [SAQ A](https://www.pcisecuritystandards.org/documents/SAQ_A_v3.pdf). Card-not-present, all cardholder data functions are fully outsourced
    + [SAQ A-EP](https://www.pcisecuritystandards.org/documents/SAQ_A-EP_v3.pdf). Partially outsourced eCommerce using a third-party website for payment processing
    + SAQ B. Imprint or standalone machines (including B-IP and P2PE), no electronic cardholder data storage (not applicable to eCommerce channels).
    + SAQ C. Payment Application Systems connected to the Internet or Web-based virtual terminals (C-VT), no electronic cardholder data storage (not applicable to eCommerce channels).
    + [SAQ D](https://www.pcisecuritystandards.org/documents/SAQ_D_v3_Merchant.pdf). All other merchants/service providers

### Third-parties
* How do you manage service providers with whom cardholder data is shared/made accessible?
    * What legal documentation do you maintain with/for them?
    * How do you engage them?  What due diligence do you conduct?
    * How do you monitor their compliance? (e.g. annual assessment)
    * How do you distribute your PCI DSS requirements across those service providers?

### Payment pages
Choosing between SAQ A and SAQ A-EP can be difficult, but there is help in the [Understanding SAQs](https://www.pcisecuritystandards.org/documents/Understanding_SAQs_PCI_DSS_v3.pdf) guidance.
* Is there any program or application code that does or _could_ capture payment information? (e.g. javascript on payment pages)
* Do all elements of payment pages originate from the third-party service provider?
* How does the system link to or embed the third-party payment processing service provider?
* How and where is the payment form created?

### Cardholder data
* Do you store any cardholder data, such as Primary Account Number (PAN), expiration date, cardholder name or CV2?
    * If so, do you store it electronically or in hardcopy?  Name all the places where this data is stored.
    * Do you receive any reports or receipts featuring cardholder data?
* For each physical data storage location:
    * How are the media secured?
    * How do you restrict physical access to the media?
    * How is distribution controlled?
    * How is the media classified, transmitted, approved for access or transmission, destroyed after use, stored prior to destruction etc.?
* For each electronic storage location (including storage locations managed by a third-party service provider):
    * How do you define the Cardholder Data Environment (CDE)?
    * If hosted on a non-networked computer, how is the host machine isolated?
    * If hosted on a networked computer, how is the network segmented?
    * If hosted by a networked third-party:
        * How is your office network segmented?
        * How is the system segmented from the third-party service provider?

### Staff access
* Which employees have access to cardholder data?
    * What audit process wraps their access to it?
    * What credentials are required for their access?
    * How are those credentials secured (e.g. password requirements)?  How and when are they rotated?
    * Do you have a policy that covers information security?
    * How often are staff trained in information security and how is that logged?

### SAQ A
* How do you meet the SAQ A requirements?
    * 9 Restrict physical access to cardholder data
    * 12 Maintain a policy that addresses information security for all personnel?

### SAQ A-EP and SAQ D
* In addition to SAQ A above, how do you meet the SAQ A-EP/D requirements?
    * 1 Install and maintain a firewall configuration to protect data
    * 2 Do not use vendor-supplied defaults for system passwords and other security parameters
    * 3 Protect stored cardholder data
    * 4 Encrypt transmission of cardholder data across open, public networks
    * 5 Protect all systems against malware and regularly update anti-virus software or programs
    * 6 Develop and maintain secure systems and applications
    * 7 Restrict access to cardholder data by business need to know
    * 8 Identify and authenticate access to system components
    * 10 Track and monitor all access to network resources and cardholder data
    * 11 Regularly test security systems and processes

There is no substitute for a thorough compliance assessment against GDPR and PCI DSS conducted by a Qualified Security Assessor (QSA), but these questions are a useful indicator of a business's readiness.  Any formal PCI assessment should begin with the [PCI DSS Self-assessment questionnaire](https://www.pcisecuritystandards.org/documents/SAQ_InstrGuidelines_v3-1.pdf).

## Code review
### Standards
* Do you provide any recommendations, guidelines or rigid technical standards to your development teams?
* What Key Performance Indicators (KPIs) do you monitor for the technical team's output?

### Software architecture
* Who decides the distribution of functional responsibility across the code?
* How are those design decision disseminated?
* What design patterns are used in the code?
* How do you ensure consistency of approach in a multi-developer team?

### Secure coding practices
* How are dependencies handled?
* What kind of scanning do you use?
* What is your policy on input sanitisation (SQL injection, XSS) and form forgeries (CSRF)?
* How do you treat authentication (including any tokens) and authorisation (including privilege escalation)?
* Do you treat input from the database as potentially hostile?

### Logging
* What log-levels does the code issue messages at?
* How verbose and accurate are those messages at each level?
* How relevant are the messages, specifically in relation to user journeys, tests, documented requirements, operation needs?

### Test coverage
* What level of unit test coverage is acceptable?
* What is the current level of test coverage?
* Do you practice test-driven development?
* What is the balance between unit tests and integration tests?
* Who performs system testing?
* How are user acceptance tests written and executed and by whom?

### Documentation
* What standards do you enforce around commenting?
* What value do you ascribe to doc blocks or inline comments?
* What documentation do you maintain and how does that link to the source?
* Tabs or spaces?  (Only kidding)

If you'd like Lightenna to audit some part of your digital estate, or conduct some due diligence on an investment that you're considering, please [get in touch](/contact).

