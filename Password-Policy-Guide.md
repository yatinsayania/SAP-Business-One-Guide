Password Policy Guide for SAP Business One
This guide is intended for the SAP-Business-One-Guide repository and gives maintainers, administrators, and contributors a practical password policy baseline for SAP Business One environments. It is written to improve repository quality by documenting secure, usable, and auditable password practices in one place.

Purpose
A password policy should do two things at the same time: reduce avoidable account risk and stay usable enough that people can follow it consistently. SAP guidance for password-policy design stresses balancing security with usability, while GitHub recommends documenting security-related practices in repository files so projects are easier to understand and maintain.

SAP Business One controls
SAP Business One provides password administration controls under Administration > Setup > General > Security > Password Administration, where administrators can set security level, expiration, minimum length, uppercase and lowercase requirements, digit requirements, non-alphanumeric requirements, password history, and the allowed number of failed logon attempts before account lockout.

In user administration, passwords can also be changed from Administration > Setup > General > Users, which is useful when onboarding users, handling credential resets, or enforcing updated policy rules.

Recommended baseline
The following baseline is a practical starting point for most SAP Business One deployments:

Setting	Recommended value	Why it helps
Minimum length	10 characters	Longer passwords are generally harder to guess, and SAP Business One supports configurable minimum length controls.
Uppercase letters	At least 1	Adds character variety supported by SAP Business One password administration.
Lowercase letters	At least 1	Prevents overly simple all-caps or numeric-only patterns.
Digits	At least 1	Increases resistance to basic guessing patterns.
Special characters	At least 1	Adds another required character class available in SAP Business One settings.
Password history	5 previous passwords blocked	SAP Business One can prevent reuse of previous passwords, reducing rotation back to familiar credentials.
Expiration	90 days where policy or regulation requires it	SAP systems allow expiration settings, but policy should reflect business and compliance needs rather than force unnecessary resets.
Account lockout	5 failed attempts	SAP Business One supports failed-logon thresholds to slow brute-force attempts.
Policy rules
Use passphrases or strong passwords that are easy for the user to remember but difficult for others to guess. Avoid names, company names, keyboard patterns, shared team passwords, and recycled credentials from older systems.

Do not share SAP Business One user accounts between employees, because shared credentials weaken accountability and make audits less reliable. Individual accounts make it easier to trace changes, enforce lockouts, and reset access in a controlled way.

Temporary or reset passwords should be changed immediately after first login. For service-style users such as B1SiteUser, SAP documents a controlled reset process through the authentication service administration console, which should be limited to authorized administrators.

Administration workflow
Open SAP Business One and go to Administration > Setup > General > Security > Password Administration.

Set the required complexity, password history, expiration, and failed-logon threshold values.

Review user records under Administration > Setup > General > Users when creating, changing, or resetting accounts.

Communicate the rules to users before enforcement so the rollout does not create unnecessary helpdesk volume.

Revisit the settings regularly after audits, incidents, or major access-model changes.

Repository placement
To make the repository easier to navigate, place this file in the repository root or inside a docs/ folder. GitHub documentation also notes that repository-level security documentation is typically added as Markdown files in the root, docs, or .github locations, depending on purpose.

A practical structure for the repository could look like this:

text
SAP-Business-One-Guide/
├── README.md
├── Password-Policy-Guide.md
├── SECURITY.md
└── docs/
    └── administration-notes.md
Suggested README link
Add a link from README.md so visitors can find the guide quickly:

text
## Security and Access
- [Password Policy Guide](./Password-Policy-Guide.md)
- [Security Policy](./SECURITY.md)
Maintenance notes
Keep the guide aligned with the actual settings used in production or test environments. A repository looks more trustworthy when the documented policy matches the system configuration and when security documentation is reviewed as part of normal change control.
