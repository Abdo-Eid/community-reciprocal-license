# Real-world use cases for CRL

This guide illustrates how the proposed Community Reciprocal License would apply in realistic software projects. These are hypothetical scenarios, not claims about the actual licensing or conduct of any named company. The [complete license](CRL-1.0.txt) controls. This guide is not an amendment or legal advice; the draft remains pending independent legal review.

## Variant scope

Sections 1–6 below describe the original CRL Standard 1.0. The new [CRL Distribution 1.0](CRL-D-1.0.txt) changes the internal deployment trigger, as illustrated in section 7. Both retain the same commercial restrictions. See [COMPARISON.md](COMPARISON.md).

## 1. LLM observability and AI monitoring

Consider a self-hostable platform in the same product category as Langfuse, with trace ingestion, dashboards, evaluation, analytics and prompt management. Assume its core is licensed under CRL.

| Scenario | Treatment under CRL | Why |
| --- | --- | --- |
| A startup monitors its paid AI application's prompts, costs, latency and errors using an unmodified self-hosted instance. | Permitted without royalties or upstream submissions. | Internal business use is allowed even when the monitored application earns revenue (3.2(b), 5.7). |
| A bank monitors internal AI agents on its own infrastructure. | Permitted. | Company size, industry and volume do not determine the license fee (3.2(b)). |
| A company improves the ingestion engine and deploys the modified build internally. | Public source sharing and upstream submission required within 30 calendar days. | Deployment triggers reciprocity even without external distribution (5.1–5.3). |
| An engineer experiments with a new trace sampling algorithm in an isolated development environment. | No contribution obligation yet. | Private, non-operational experimentation is exempt (2.6, 5.1). |
| A cloud vendor offers dedicated managed instances of the platform for a monthly fee. | Separate written authorization required. | Dedicated instances are not an exception to the hosted-service restriction (3.3, 4.1). |
| A competitor replaces the dashboard and exposes the same core tracing and evaluation features through a paid API. | Separate written authorization required if the offering relies on licensed rights and exposes substantial functionality. | Rebranding and API wrappers do not bypass section 4. |
| A business exposes a small status widget showing its own application's uptime to paying customers. | Potentially permitted, depending on scope. | Incidental metrics in an independently valuable product are distinguishable from selling observability functionality itself (3.2(c), 4.3). |
| A company offers a paid multi-tenant customer portal with trace search, evaluation and analytics powered by the CRL server. | Likely requires authorization. | The portal may offer material characteristic capabilities as a service in their own right (4.1–4.3). |
| A customer connects a separately developed OpenTelemetry exporter or independent SDK. | The independent component is not automatically covered. | Interoperability alone is not a modification (2.4, 6.2). |
| A company hosts the platform on ordinary rented cloud compute and operates it itself. | Permitted for internal use. | General-purpose infrastructure is distinct from managed application hosting (3.3). |

### Data and confidentiality

The monitored applications, customer prompts, traces, logs, credentials, private datasets and unrelated business systems do not become subject to CRL merely because the platform processes them. Sections 2.5, 3.2 and 5.6 distinguish covered source modifications from unrelated data and systems. A modification itself cannot be hidden simply by calling it confidential; remove secrets without withholding required source, or obtain separate permission if lawful disclosure is impossible. CRL does not replace privacy agreements, data protection law, or a hosted service's data retention/export commitments.

### Suggested component licensing (optional architecture)

For an observability product, a maintainer could license independently developed SDKs, API specifications, exporters and integrations under Apache-2.0 or MIT, while placing the server, dashboard, evaluation and analytics engines under CRL. Commercial modules may have separate terms if the necessary rights are held. Explicit file/package boundaries, dependency notices and separate license files are essential. This is an optional product-design choice, not a requirement or exemption created by CRL.

## 2. Other software categories

| Product category | Permitted internal or independent use | Commercial offering requiring authorization |
| --- | --- | --- |
| Workflow automation | A retailer automates order processing and internal reports. | A vendor sells access to the covered workflow builder as a hosted automation platform. |
| Analytics and BI | A consultancy uses the dashboard internally to prepare and sell independent reports. | A provider sells customers subscriptions to the covered dashboard and its analytics capabilities. |
| Developer tools | A software team runs a code analysis tool in its internal CI pipeline. | A vendor wraps the tool into a paid hosted code-analysis service exposing its characteristic functionality. |
| AI document processing | An accounting firm uses the tool internally to prepare independent client deliverables. | A vendor sells on-demand access to the same extraction engine through a paid API. |
| Infrastructure monitoring | A company monitors its own production systems. | A provider sells access to the covered monitoring platform as a managed application. |
| Internal administration | An organization self-hosts a tool to manage its own operations. | A reseller bundles copies of the tool with a paid product license. |

The examples assume that the offering involves rights granted by CRL. The distinction is the substance of the offering, not whether an organization is for-profit, uses a different UI or charges a separate fee. See sections 3 and 4. Borderline services require individual assessment.

## 3. Contributions and practical compliance

| Scenario | What to do |
| --- | --- |
| Run the original release unchanged. | No upstream submission or usage reporting is required solely for use (5.7). |
| Deploy a modified version in production. | Publish exact corresponding source and offer changes upstream within 30 calendar days of first deployment (5.1–5.3). |
| Publish a modified fork or distribute modified binaries. | Make corresponding source public no later than first distribution; submit changes upstream within 30 calendar days. Include the license, notices and source links as applicable (5, 6). |
| Maintainer rejects or ignores a pull request. | A good-faith submission satisfies the upstream requirement; keep the public source available as required (5.2–5.3). |
| Upstream repository is archived or inaccessible. | Publish source on time, document attempted submission and use an identified alternative contact if available (5.4). |
| A vulnerability fix needs coordinated disclosure. | Disclose confidentially by the ordinary deadline; delay public release only as reasonably necessary, up to 90 additional days without authorized extension. Do not distribute modified versions publicly while withholding corresponding source (5.5). |
| A company cannot legally publish its modifications. | Do not deploy or distribute those modifications under CRL, or cease the affected activity and obtain separate authorization (5.6). |

### Example timeline

- Day 0: a company first deploys a modified trace-ingestion engine internally.
- By day 30: publish the corresponding source and make a good-faith upstream submission, assuming no earlier distribution deadline and no applicable security exception.
- If upstream rejects the patch: continue using the compliant public fork; no merge or additional development is required.
- Keep exact source available throughout deployment and for at least 12 months after the last deployment or distribution of that version, whichever is later (5.2).

The deadline applies to each material revision; minor revisions can be grouped only if the relevant deadlines and exact-source requirements are satisfied.

## 4. SaaS, consulting, and commercial licensing

| Scenario | Treatment |
| --- | --- |
| A consultant charges for installing the platform on a customer's own environment under the customer's operational control. | Permitted for genuine independent labor, subject to sections 3.2(f), 3.3 and 5–7. |
| A consultant develops a commissioned modification and delivers it to the customer for a labor fee. | Potentially permitted under 3.2(f); source sharing and upstream obligations still apply. |
| A reseller charges for prepackaged modified builds or bundles access with paid support. | Generally requires separate authorization (3.2(f), 4). |
| A developer hosts a genuinely noncommercial public demo with no commercial consideration. | Permitted subject to the other terms (3.2(e), 4–7). |
| A provider offers free access but monetizes it through advertising or uses it to promote a commercial edition of the covered product. | Separate authorization required if the offering meets section 4's commercial test. |
| The original rights holder launches a paid hosted edition. | Permitted for material the holder owns or is authorized to commercially license (8.3). |
| A maintainer sells a proprietary edition containing external contributions. | Requires sufficient rights in those contributions; consider a separately accepted CLA. CRL alone does not grant those rights (8.1, 8.3). |

## 5. Forks, AI-assisted changes and competition

- An AI-assisted refactor or translation of protected covered code remains subject to CRL where permission from the relevant rights holder is required (2.4, 4.4).
- Noncommercial public forks are permitted under the same license with source sharing, upstream submission and attribution as applicable.
- A developer who independently implements the same idea without infringing protected material is not bound by CRL merely because the resulting product competes with the original.
- Contributors may retain copyright in their own work. Maintainers are not required to merge every contribution.

## 6. Quick decision guide

1. Does your use require rights in the covered work? If not, CRL does not independently restrict it.
2. Are you offering the covered software or its substantial functionality externally for commercial benefit? If yes, obtain written authorization from the necessary rights holders unless a specific exception applies.
3. Are you deploying or distributing a modification? If yes, comply with section 5's corresponding-source and upstream deadlines, even for internal deployment.
4. Are you redistributing copies? Preserve notices, the license and applicable source access under sections 6–7.
5. Are you planning proprietary relicensing or accepting third-party contributions? Check ownership, dependency licenses and separate permissions.

When uncertain, consult the [full CRL v1.0 text](CRL-1.0.txt), the [FAQ](FAQ.md) and qualified legal counsel. This document does not create new permissions or obligations.

## 7. Distribution variant examples

| Scenario | Standard | Distribution |
| --- | --- | --- |
| Voice team adds an acoustic-analysis view to its internally deployed debugger | Publish and offer upstream within 30 days | May remain private |
| Observability team privately deploys a custom ingestion engine | Publish and offer upstream within 30 days | May remain private |
| Developer publishes a modified fork | Source at first distribution; upstream within 30 days | Same |
| Organization sends modified binaries to an independent customer under NDA | Distribution triggers sharing | Same, unless controlled-access exception applies |
| A nonprofit provides a modified tracing dashboard to external invited users for free | Reciprocity triggered by operational deployment | Reciprocity triggered by external offering; source and upstream within 30 days |
| A paid hosted replay or observability service exposes substantial covered functionality | Authorization required | Same |
| A previously distributed modification returns to internal-only use | Already-triggered obligations survive | Same; retention period follows CRL-D section 5.2 |

The Distribution variant does not authorize commercial services forbidden by section 4. Incidental backend use and independent integrations remain distinct from offering substantial functionality. See the selected operative license for precise deadlines, exceptions and retention requirements.
