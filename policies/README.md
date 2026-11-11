# Compliance Policy Library (Rego)

This directory contains the Open Policy Agent (OPA) / Rego compliance policies enforcing NIST 800-53 controls against Terraform plans:

| Policy File | Control ID | Severity | One-Line Remediation |
| :--- | :--- | :--- | :--- |
| `sc28_encryption.rego` | **SC-28** | `high` | Add an `encryption { default_kms_key_name = ... }` block referencing a `google_kms_crypto_key` you control. |
| `ac3_no_public.rego` | **AC-3** | `critical` | Set `uniform_bucket_level_access = true`, `public_access_prevention = "enforced"`, and narrow firewall `source_ranges` or remove public management port rules (`22`, `3389`). |
| `cm6_required_tags.rego` | **CM-6** | `medium` | Add the four required labels (`project`, `environment`, `managed_by`, `compliance_scope`) to the resource. |
