# Compliant GCS Bucket Module

This reusable Terraform module enforces NIST 800-53 controls SC-12 (cryptographic key establishment via Cloud KMS keyring and customer-managed key), SC-13 and SC-28 (encryption at rest with a CMEK rotating every 90 days), AU-11 (audit and object record retention enforced by environment), CM-6 (baseline configuration via object versioning and non-overridable compliance labels), and AC-3 (enforced public access prevention and uniform bucket-level access).
