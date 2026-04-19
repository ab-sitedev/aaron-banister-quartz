---
publish: true
created: 2026-03-17T18:53:19.475-05:00
modified: 2025-11-27
---

Access grants represent applications a user has access to. They describe when the access starts and ends (complimented by an Active flag), and of course who the access was granted to.

| Field  | Purpose                                      |
| ------ | -------------------------------------------- |
| Access | References a [[Business Application]] record |
| User   | References a User record                     |
| Start  | When the access starts                       |
| End    | When the access expires or was removed       |
| Active | True until access expires or is removed      |
