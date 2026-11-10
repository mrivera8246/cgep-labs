# Compliant S3 Bucket Primitive

This module enforces NIST 800-53 controls SC-28 (encryption at rest via AES-256), AU-3 and AU-6 (server access logging to a dedicated, locked-down log bucket), CM-6 (baseline configuration via mandatory compliance tags and object versioning), and AC-3 (explicit public access block across all four vectors) on an AWS S3 bucket.
