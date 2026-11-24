# CRL Standard vs. CRL Distribution

Both are proposed source-available licenses, pending independent legal review. Choose one explicitly; neither is automatically interchangeable with the other.

| Topic | [CRL Standard 1.0](CRL-1.0.txt) | [CRL Distribution 1.0](CRL-D-1.0.txt) |
| --- | --- | --- |
| Personal and internal business use | Free | Free |
| Private experimentation | No contribution required | No contribution required |
| Internal production modifications | Publish source and offer upstream within 30 days | May remain private if not distributed or externally offered |
| Distribution of modified copies, even privately to independent parties | Publish source at first distribution; offer upstream within 30 days | Same |
| Permitted external offering of modified substantial functionality | Deployment triggers reciprocity within 30 days | External offering triggers reciprocity within 30 days, even if invitation-only |
| Paid hosted services and unauthorized commercial resale | Separate written authorization required | Same |
| Independent integrations and outputs | Permitted subject to sections 2–4 | Same |
| Copyright and attribution | Preserve notices | Same |
| Separate commercial licensing | Requires relevant rights | Same |
| Source retention | Throughout deployment and at least 12 months after last deployment or distribution, whichever is later | Throughout external offering and at least 12 months after last external offering or distribution, whichever is later |

## What changed in CRL-D?

Sections 2 and 5 define and implement the external-offering trigger; sections 9 and 11 align survival and variant identity. Section 4's commercial restrictions are unchanged. An external offering is remote access to substantial functionality in its own right by outsiders, not incidental use within an independent product or controlled access by personnel acting on the organization's behalf.

The new variant is deliberately not restricted to public forks: distributing a modified copy privately to an independent customer triggers source sharing, subject to the controlled-access exception. A confidential commissioned delivery may also trigger disclosure. A company may operate its own modified version privately without upstream obligations, including in production. Once disclosure obligations arise, returning to internal use does not cancel them.

Neither license is OSI-approved. Custom SPDX references: `LicenseRef-CRL-1.0` (Standard) and `LicenseRef-CRL-D-1.0` (Distribution). These are not registered SPDX identifiers.

See [CHOOSING.md](CHOOSING.md) and [USE_CASES.md](USE_CASES.md). The operative license texts control.
