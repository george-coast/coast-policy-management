**Account Management Policy**

**1\. Purpose**  
The purpose of this Account Management Policy is to define procedures for creating, managing, monitoring, and disabling accounts to ensure authorized access to the organization’s systems and information. This policy aligns with NIST 800-53 to maintain confidentiality, integrity, and availability.

**2\. Scope**  
This policy applies to all user, service, and privileged accounts on the organization’s systems, networks, applications, and cloud environments. It includes employees, contractors, vendors, and other third parties.

**3\. Policy Statement**

**3.1 Account Creation**

- User accounts must be created through an approved request and authorization process.
- New accounts must be associated with a specific individual or role and tied to unique identifiers.
- Service accounts for automated tasks must follow the same approval process and include documentation of their intended use.

**3.2 Account Management**

- **Role-Based Access Control (RBAC):** Access levels for all accounts must align with job responsibilities or operational requirements.
- Privileged accounts (e.g., administrator accounts) must be strictly limited to authorized personnel.
- Shared accounts are prohibited unless explicitly approved for operational needs and documented.

**3.3 Account Monitoring and Auditing**

- User account activity must be logged and monitored for anomalies, especially for privileged accounts.
- All accounts must be reviewed quarterly to confirm alignment with user roles.
- Orphaned accounts must be identified and deactivated promptly.

**3.4 Password Management**

- Passwords must comply with the organization’s password policy (e.g., minimum length, complexity, expiration rules).
- Default system passwords must be changed before deployment.
- Password resets must require verification of the account holder’s identity.

**3.5 Account Suspension and Termination**

- Accounts must be disabled immediately upon an employee’s termination, transfer, or role change that no longer requires access.
- Inactive accounts must be disabled after 30 days and removed after 90 days unless otherwise approved.
- Emergency account suspensions may occur for suspected malicious activity or policy violations.

**3.6 Temporary Accounts**

- Temporary or guest accounts must be approved, documented, and set to expire automatically after a defined period (e.g., 7 days).
- Contractors and vendors must use temporary accounts with limited access based on contractual obligations.

**3.7 Service Accounts**

- Service accounts must not be used for interactive logins.
- Passwords for service accounts must comply with the password policy and be rotated regularly.

**3.8 Account Lockout**

- User accounts must lock automatically after a defined number of failed login attempts (e.g., 5) and require manual intervention for unlocking.

**4\. Roles and Responsibilities**

**4.1 System Administrators**

- Approve account creation, modifications, and terminations.
- Monitor accountancy and enforce policy compliance.

**4.2 Security Team**

- Conduct regular audits of user accounts and access rights.
- Investigate and remediate unauthorized account activity.

**4.3 Managers and Supervisors**

- Approve access requests for employees under their supervision.
- Notify the security team immediately of personnel changes affecting access.

**4.4 All Users**

- Maintain the security of their accounts and report suspicious activities.

**5\. Enforcement**  
Violations of this policy may result in disciplinary action, up to and including termination of employment, and/or legal action.

**6\. Review and Revision**  
This policy shall be reviewed annually or after significant changes in the organizational structure, systems, or regulatory requirements.

**7\. References**

- NIST SP 800-53 Rev. 5: Access Control (AC) Family
- Organization’s Password Policy
- Identity and Access Management Procedures
