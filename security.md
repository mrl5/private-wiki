# Security grab-bag

[The Rugged Manifesto](https://ruggedsoftware.org/)
> I am rugged and, more importantly, my code is rugged.
> I recognize that software has become a foundation of our modern world.
> I recognize the awesome responsibility that comes with this foundational role.
> I recognize that my code will be used in ways I cannot anticipate, in ways it was not designed, and for longer than it was ever intended.
> I recognize that my code will be attacked by talented and persistent adversaries who threaten our physical, economic, and national security.
> I recognize these things - and I choose to be rugged.
> I am rugged because I refuse to be a source of vulnerability or weakness.
> I am rugged because I assure my code will support its mission.
> I am rugged because my code can face these challenges and persist in spite of them.
> I am rugged, not because it is easy, but because it is necessary and I am up for the challenge.


## Table of contents
* [Fundamentals](#fundamentals)
* [AWS](#aws)
* [MACs](#macs)
* [Notable Literature](#notable-literature)
* [Programming](#programming)


## Fundamentals

* predict prevent detect respond
  - https://www.nist.gov/cyberframework/online-learning/five-functions
  - https://www.gartner.com/doc/3286317/using-predict-prevent-detect-respond
* [InfoSec](https://en.wikipedia.org/wiki/Information_security)
  - [security principles](https://dwheeler.com/secure-programs/Secure-Programs-HOWTO/security-principles.html)
  - [CIA triad](https://en.wikipedia.org/wiki/Information_security#Key_concepts)
  - [security classification](https://en.wikipedia.org/wiki/Classified_information)
  - [access control](https://en.wikipedia.org/wiki/Information_security#Access_control)
* [GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=PL)
* [threat modeling](https://en.wikipedia.org/wiki/Threat_model)
  - [OWASP on application threat modeling](https://www.owasp.org/index.php/Application_Threat_Modeling)
  - [STRIDE](https://en.wikipedia.org/wiki/STRIDE_(security))
* [Secure Software Development Life Cycle](https://www.owasp.org/index.php/OWASP_Secure_Software_Development_Lifecycle_Project)
  - [Good Security Design Principles](https://dwheeler.com/secure-programs/Secure-Programs-HOWTO/follow-good-principles.html)
  - [OWASP Application Security Verification Standard]
  - [OWASP OpenSAMM](https://www.opensamm.org/)
  - [OWASP Comprehesive, Lightweight Application Security Process](https://www.owasp.org/index.php/CLASP_Concepts)
  - [The Building Security In Maturity Model](https://www.bsimm.com/framework.html)
  - [Microsoft Security Development Lifecycle Practices](https://www.microsoft.com/en-us/securityengineering/sdl/practices)

### Must-know links

* [OWASP](https://www.owasp.org/index.php/Main_Page)
* [RFC](https://www.rfc-editor.org/rfc-index.html)
* [CVE security vulnerability database](https://www.cvedetails.com/)
* [National Vulnerability Database](https://nvd.nist.gov/vuln)

### Auditing
* https://wiki.gentoo.org/wiki/Project:Auditing

### Integrity
* https://wiki.gentoo.org/wiki/Project:Integrity

### Random
- [Security 101 for SaaS startups](https://github.com/forter/security-101-for-saas-startups/blob/english/security.md)


## AWS
* [AWS Security Best Practices](https://d1.awsstatic.com/whitepapers/Security/AWS_Security_Best_Practices.pdf)
* [CIS Amazon Web Services Foundations](https://d1.awsstatic.com/whitepapers/compliance/AWS_CIS_Foundations_Benchmark.pdf)
* [Navigating GDPR Compliance on AWS](https://d1.awsstatic.com/whitepapers/compliance/GDPR_Compliance_on_AWS.pdf)
* [Amazon S3 Block Public Access -- Another Layer of Protection for Your Accounts and Buckets](https://aws.amazon.com/blogs/aws/amazon-s3-block-public-access-another-layer-of-protection-for-your-accounts-and-buckets/)
* tools:
  * [prowler](https://github.com/toniblyx/prowler) - AWS Security Best Practices Assessment, Auditing, Hardening and Forensics Readiness Tool
  * [ScoutSuite](https://github.com/nccgroup/ScoutSuite) - multi-cloud security-auditing tool
  * [aws_public_ips](https://github.com/arkadiyt/aws_public_ips) - tool to fetch all public IP addresses (both IPv4/IPv6) associated with an AWS account
  * [PMapper](https://github.com/nccgroup/PMapper) - script and library for identifying risks in the configuration of IAM in an AWS account
  * [awspx](https://github.com/FSecureLABS/awspx) - graph-based tool for visualizing effective access and resource relationships within AWS
  * [Cartography](https://github.com/lyft/cartography) - consolidates infrastructure assets and the relationships between them in an intuitive graph view
  * [aws-key-disabler](https://github.com/te-papa/aws-key-disabler) - Lambda Function that disables AWS IAM User Access Keys after a set amount of time
  * [Policy Sentry](https://github.com/salesforce/policy_sentry) - IAM Least Privilege Policy Generator, auditor, and analysis database
  * [LambdaGuard](https://github.com/Skyscanner/LambdaGuard) - AWS Lambda auditing tool
  * [Repokid](https://github.com/Netflix/repokid) - remove permissions granting access to unused services from the inline policies of IAM roles in an AWS account
  * [CFRipper](https://github.com/Skyscanner/cfripper) - Library and CLI tool for analysing CloudFormation templates and check them for security compliance
  * [Cloud Custodian](https://cloudcustodian.io/) - rules engine for cloud security, cost optimization, and governance, DSL in yaml for policies to query, filter, and take actions on resources
  * [Cloud Inquisitor](https://github.com/RiotGames/cloud-inquisitor) - resource ownership, domain hijacking
  * [Asecure](https://asecure.cloud/) - web app for generating security-related configs
  * [Terraform-aws-secure-baseline](https://github.com/nozaq/terraform-aws-secure-baseline) - Terraform module to set up your AWS account with the resonably secure configuration baseline
* (AWS re:Invent 2020) Ten easy and effective ways to secure your AWS
  environment:
  1. Amazon S3 Block Public Access
  2. Use federation - make all your IAM credentials temporary
  3. Collect AWS CloudTrail for your entire AWS organization
  4. Know how to query a CloudTrail
  5. Tag your subnets for scalable control over connectivity
  6. Centrally manage network security with AWS Firewall Manager
  7. Assert network origin in your AWS IAM policies
  8. Use the network to keep your data where you want
  9. Connect to your Amazon EC2 instances without SSH keys: do this `aws ssm
     start-session --target i-01234567` instead of `ssh user@host`
  10. Monitor DNS from your VPC with Amazon Route 53 Resolver Query Logging


## MACs
* SELinux
  - https://wiki.gentoo.org/wiki/Project:SELinux
  - https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/selinux_users_and_administrators_guide/index
  - https://selinuxproject.org/page/Main_Page
* AppArmor
  - https://debian-handbook.info/browse/stable/sect.apparmor.html
  - https://gitlab.com/apparmor/apparmor/wikis/Documentation


## Notable Literature
* [Secure Programming HOWTO](https://dwheeler.com/secure-programs/Secure-Programs-HOWTO/index.html)
* [The Tangled Web: A Guide to Securing Modern Web Applications](http://lcamtuf.coredump.cx/tangled/)
* [Silence on the Wire: A Field Guide to Passive Reconnaissance and Indirect Attacks](http://lcamtuf.coredump.cx/silence.shtml)
* [The Web Application Hacker's Handbook: Finding and Exploiting Security Flaws, 2nd Edition](https://www.wiley.com/en-us/The+Web+Application+Hacker%27s+Handbook%3A+Finding+and+Exploiting+Security+Flaws%2C+2nd+Edition-p-9781118026472)
* [OWASP Application Security Verification Standard]


## Programming
* [Secure Programming HOWTO - Creating Secure Software](https://dwheeler.com/secure-programs/) *document includes specific guidance for a number of languages, including C, C++, Java, Perl, Python, and Ada95*
* [SEI CERT Coding Standards](https://wiki.sei.cmu.edu/confluence/display/seccode/SEI+CERT+Coding+Standards) *coding standards for commonly used programming languages such as C, C++, Java, and Perl, and the Android™ platform*
* [seccomp](https://en.wikipedia.org/wiki/Seccomp)
  - https://www.kernel.org/doc/Documentation/prctl/seccomp_filter.txt


[OWASP Application Security Verification Standard]: https://www.owasp.org/images/d/d4/OWASP_Application_Security_Verification_Standard_4.0-en.pdf
