# ✅ GDPR Compliance Checklist – Web-based Booking System

| Section                         | Question                                                                                          | Result | Justification |
|---------------------------------|---------------------------------------------------------------------------------------------------|--------|---------------|
| **Personal data mapping and minimization** | Have all personal data collected and processed in the system been identified? (e.g., name, email, age, username) | ✅ | Name, email, age, username clearly used in registration. |
|                                 | Have you ensured that only necessary personal data is collected (data minimization)?             | ✅ | Registration requires only name, email, password, age. |
|                                 | Is user age recorded to verify that the booker is over 15 years old?                             | ✅ | System checks age when booking. |
| **User registration and management** | Does the registration form include GDPR-compliant consent for processing personal data (e.g., acceptance of the privacy policy)? | ⚠️ | No checkbox/explicit consent during registration. |
|                                 | Can users view, edit, and delete their own personal data via their account?                      | ❌ | No profile management visible. |
|                                 | Is there a mechanism for the administrator to delete a reserver in accordance with the "right to be forgotten"? | ✅ | Admin can delete reserver accounts. |
|                                 | Is underage registration (under 15 years) and booking functionality restricted?                  | ✅ | Booking requires age > 15. |
| **Booking visibility**          | Are bookings visible to non-logged-in users only at the resource level (without any personal data)? | ✅ | Public view shows only resource status. |
|                                 | Is it ensured that names, emails, or other personal data of bookers are not exposed publicly or to unauthorized users? | ⚠️ | API allowed access to other users’ booking via ID (`/api/reservations/1`). |
| **Access control and authorization** | Have you ensured that only administrators can add, modify, and delete resources and bookings?  | ✅ | Tested in Access Control Matrix. |
|                                 | Is the system using role-based access control (e.g., reserver vs. administrator)?                | ✅ | Roles are enforced. |
|                                 | Are administrator privileges limited to ensure GDPR compliance?                                 | ⚠️ | No log of actions or protection against misuse of admin role. |
| **Privacy by Design Principles**| Has Privacy by Default been implemented (e.g., collecting the minimum data by default)?          | ✅ | Minimal data is collected by design. |
|                                 | Are logs implemented without unnecessarily storing personal data?                               | ⚠️ | Unclear how logs are handled. |
|                                 | Are forms and system components designed with data protection in mind (e.g., secured login, minimal fields)? | ✅ | Forms use minimal input; login is protected. |
| **Data security**               | Are CSRF, XSS, and SQL injection protections implemented?                                        | ⚠️ | ZAP reports noted absence of CSRF tokens. |
|                                 | Are passwords securely hashed using a strong algorithm (e.g., bcrypt, Argon2)?                  | ✅ | bcrypt used in backend. |
|                                 | Are data backup and recovery processes GDPR-compliant?                                          | ❌ | No info available on backups. |
|                                 | Is personal data stored in data centers located within the EU?                                  | ⚠️ | Unknown hosting location. |
| **Data anonymization and pseudonymization** | Is personal data anonymized where possible?                                                | ❌ | Data shown in clear format in internal views. |
|                                 | Are pseudonymization techniques used to protect data while maintaining its utility?             | ❌ | Not implemented. |
| **Data subject rights**         | Can users download or request all personal data related to them (data access request)?          | ❌ | No such functionality available. |
|                                 | Is there an interface or process for users to request the deletion of their personal data?       | ❌ | Admin can delete accounts, but no self-service. |
|                                 | Can users withdraw their consent for data processing?                                           | ❌ | Consent is not clearly collected in first place. |
| **Documentation and communication** | Is there a privacy policy available to users during registration and easily accessible?        | ⚠️ | `/privacypolicy` exists but is empty without content unless created manually. |
|                                 | Are administrators and developers provided with documented data protection practices and processing activities? | ❌ | No visible internal documentation. |
|                                 | Is there a documented data breach response process (e.g., how to notify authorities and users of a breach)? | ❌ | Not mentioned in policies or app. |
