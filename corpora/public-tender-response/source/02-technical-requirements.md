# NOVA-DOC 2027 — technical requirements

| ID | Requirement |
|---|---|
| ARCH-01 | All production data, backups and operational logs shall remain within the European Union. Production shall run in a private-cloud tenant dedicated to NMA. |
| ARCH-02 | The service shall expose documented REST APIs and support SAML 2.0 and OpenID Connect federation. |
| MIG-01 | The supplier shall migrate 2.4 million documents and 12 TB of content while preserving folder structure, creation date, author and the 14 metadata fields listed in Appendix A. |
| MIG-02 | A representative pilot containing at least 100,000 documents shall be accepted before production migration begins. |
| PLAN-01 | The pilot shall be ready by 30 June 2027. The initial production target is 31 October 2027, subject to published clarifications. |
| SLA-01 | Monthly production availability shall be at least 99.95%, excluding at most four hours of announced maintenance per month. |
| SLA-02 | Priority-1 incidents require acknowledgement within 15 minutes and restoration within four hours, 24 hours a day and 7 days a week. |
| SEC-01 | The supplier shall hold a valid ISO/IEC 27001 certificate covering the proposed service at the submission deadline. The certificate shall be included in the response. |
| SEC-02 | An independent penetration-test report less than 12 months old at the submission deadline shall be supplied before production go-live. Critical findings must be closed before the pilot. |
| ACC-01 | The user interface shall conform to WCAG 2.1 AA at production go-live. A dated accessibility audit shall be delivered with the response or planned before go-live. |
| TEAM-01 | The named programme lead shall have at least eight years of relevant delivery experience and be allocated at least 80% from contract start through production go-live. |
| TEAM-02 | The named solution architect shall have at least five years of relevant architecture experience and be allocated at least 50% through pilot acceptance. |
| OPS-01 | Security monitoring and Priority-1 incident coordination shall not be subcontracted. |

Requirements using “shall” are mandatory unless the evaluation document or a later clarification
explicitly says otherwise.
