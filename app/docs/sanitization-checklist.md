---
title: Data Sanitization Checklist - Template
status: Template
date_created: 2026-06-18
---

# General Data Sanitization Checklist

Template for sanitizing sensitive data in technical documents, tickets, logs, and reports.

## Pre-Sanitization

- [ ] **Input Source Identified:** Document path/name recorded
- [ ] **Output Destination Specified:** Where sanitized version will be saved
- [ ] **Original Language Noted:** Preserve or translate?
- [ ] **Data Classification Done:** What's sensitive vs. contextual?
- [ ] **Stakeholder Approval:** If needed, confirm scope of sanitization

## Redaction Rules (Tier 1) — Complete Removal

Remove entirely. Replace with `[REDACTED]`.

### Personal Identifiable Information (PII)
- [ ] Full names / person identifiers
- [ ] Date of birth / age data
- [ ] Social Security Numbers / National ID numbers
- [ ] Passport numbers / travel documents
- [ ] Driver's license / ID card numbers
- [ ] Phone numbers (complete)
- [ ] Complete email addresses
- [ ] Home addresses / physical locations
- [ ] Family member names
- [ ] Medical/health information

### Financial Data
- [ ] Credit card numbers (full)
- [ ] Card CVV/security codes
- [ ] Bank account numbers (full IBAN/routing)
- [ ] Account balances / financial amounts (if sensitive)
- [ ] Tax ID numbers (full)
- [ ] Salary / compensation data

### Secrets & Credentials
- [ ] Plaintext passwords
- [ ] API keys / authentication tokens
- [ ] Database connection strings with credentials
- [ ] SSH keys / private keys
- [ ] OAuth tokens / bearer tokens
- [ ] Session tokens / cookies with secrets
- [ ] Cloud service credentials (AWS keys, etc.)
- [ ] Internal service credentials

### Business Secrets
- [ ] Proprietary algorithm details (if confidential)
- [ ] Internal-only server/system names (optional: substitute with generic)
- [ ] Customer lists / partner names (if confidential)
- [ ] Financial metrics / revenue data (if sensitive)
- [ ] Strategic information
- [ ] Unreleased feature details

## Masking Rules (Tier 2) — Partial Obscuration

Partially hide. Preserve context for troubleshooting.

### Network & Infrastructure
- [ ] IP Addresses: `192.168.1.1` → `192.168.x.x` or `10.0.x.x`
- [ ] Hostnames: `prod-db-001.internal.com` → `prod-db-XXX.internal.com`
- [ ] Port numbers: Optional (keep for context)
- [ ] URLs: Mask domain/path details if sensitive: `https://internal.example.com/api/users/123` → `https://internal.example.com/api/users/XXX`

### Identifiers
- [ ] Email addresses: `john.doe@company.com` → `j***e@company.com`
- [ ] Usernames: `jdoe_prod` → `j***e_prod` or generic user ID
- [ ] Account/Transaction IDs: `ACC-123456789` → `ACC-XXXXXX`
- [ ] Order/Ticket IDs: Mask unique suffix if needed
- [ ] Session/Request IDs: `sess_abc123def456` → `sess_XXXXXX`

### Partial Data
- [ ] Phone numbers: `+1-555-0123` → `+1-555-XXXX`
- [ ] Social Security: `123-45-6789` → `XXX-XX-6789` (last 4 only, if needed)
- [ ] Zip codes: Keep if low-risk, mask if combined with name
- [ ] Bank routing: `021000021` → `021-XXXX` (first part only)
- [ ] IBAN: `UA90 3052 9900 0000 0260 0012 3456 789` → `UA90-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX`

## Context Preservation Checklist

Verify technical/business context remains intact for troubleshooting:

- [ ] **Error Messages:** Preserved (stack traces, error codes)
- [ ] **Method/Function Names:** Kept (code logic visible)
- [ ] **Component/Module Names:** Kept (system architecture clear)
- [ ] **Log Structure:** Timestamps, log levels, format intact
- [ ] **Variable Relationships:** Logic flow understandable
- [ ] **Numerical Context:** Amounts, counts, metrics preserved (non-financial)
- [ ] **Ticket Details:** ID, priority, status, steps to reproduce
- [ ] **Technical Specifications:** OS, version, configuration (non-sensitive)
- [ ] **Feature/Branch Names:** Kept (development context)

## Output Verification

After sanitization, verify:

- [ ] No plaintext passwords visible
- [ ] No complete credit card / financial account numbers
- [ ] No complete phone numbers
- [ ] No complete SSN / national ID / passport
- [ ] No API keys or tokens (full or partial recognizable)
- [ ] No complete email addresses (at least masked)
- [ ] No complete home addresses
- [ ] No database credentials in connection strings
- [ ] No unmasked IP addresses (if sensitive)
- [ ] No sensitive names in text
- [ ] No health/medical data
- [ ] No salary/compensation data
- [ ] No customer lists (if confidential)
- [ ] **Document Structure:** Intact and readable
- [ ] **Technical Context:** Sufficient for debugging
- [ ] **Language:** Preserved as intended
- [ ] **Formatting:** Valid Markdown/format

## Compliance & Standards

Check against relevant regulations:

- [ ] **GDPR:** Personal data minimization (EU)
- [ ] **CCPA:** Consumer privacy rights (California)
- [ ] **HIPAA:** Health data protection (US Healthcare)
- [ ] **PCI-DSS:** Payment card security
- [ ] **SOC 2:** Data protection requirements
- [ ] **Internal Policy:** Company data classification
- [ ] **NDA/Confidentiality:** Contractual requirements

## Documentation

- [ ] **Sanitization Log:** Document what was redacted/masked
- [ ] **Reason for Changes:** Note why each field was sanitized
- [ ] **Who Performed It:** Name/role of sanitizer
- [ ] **When Performed:** Date and time
- [ ] **Approval Status:** Reviewed and approved?
- [ ] **Version Control:** Track as new version if applicable

## Sign-Off Checklist

- [ ] All sensitive data removed or masked
- [ ] Technical context preserved for intended audience
- [ ] No accidental re-introduction of sensitive data
- [ ] Stakeholders reviewed (if required)
- [ ] Output document safe for distribution/storage
- [ ] Sanitization log attached or documented
- [ ] Original file archived securely (if needed)
- [ ] All steps verified and complete

---

## Usage Notes

1. **Copy this template** for each sanitization task
2. **Check off boxes** as you complete each step
3. **Customize the rules** for your data classification
4. **Document decisions** in the Sanitization Log
5. **Archive this checklist** with the sanitized output
6. **Review before publishing** the sanitized document

**Status:** Template ready for use
