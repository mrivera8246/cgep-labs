# Compliance Policy Library (Rego)

This directory contains the Open Policy Agent (OPA) / Conftest compliance policies enforcing NIST 800-53 controls against GCP and AWS Terraform plans:

| Policy File | Cloud | Namespace | Control ID | Severity | One-Line Remediation |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `sc28_encryption.rego` | **GCP** | `compliance.sc28` | **SC-28** | `high` | Add an `encryption { default_kms_key_name = ... }` block referencing a `google_kms_crypto_key` you control. |
| `ac3_no_public.rego` | **GCP** | `compliance.ac3` | **AC-3** | `critical` | Set `uniform_bucket_level_access = true`, `public_access_prevention = "enforced"`, and narrow firewall `source_ranges` or remove public management port rules (`22`, `3389`). |
| `cm6_required_tags.rego` | **GCP** | `compliance.cm6` | **CM-6** | `medium` | Add the four required labels (`project`, `environment`, `managed_by`, `compliance_scope`) to the resource. |
| `sc28_encryption_aws.rego` | **AWS** | `compliance.sc28_aws` | **SC-28** | `high` | Add an `aws_s3_bucket_server_side_encryption_configuration` resource referencing the bucket (`bucket = aws_s3_bucket.<name>.id`). |
| `ac3_no_public_aws.rego` | **AWS** | `compliance.ac3_aws` | **AC-3** | `critical` | Add an `aws_s3_bucket_public_access_block` resource referencing the bucket with all four flags (`block_public_acls`, `block_public_policy`, `ignore_public_acls`, `restrict_public_buckets`) set to `true`. |
| `cm6_required_tags_aws.rego` | **AWS** | `compliance.cm6_aws` | **CM-6** | `medium` | Add the four required tags (`Project`, `Environment`, `ManagedBy`, `ComplianceScope`) to the resource or via provider `default_tags`. |
