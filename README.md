# Awesome-Form-Filling-E-Signature

## Top Form Filling & E-Signature Tools Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Self-Hosted Document Signing, Visual Form Builders & Cryptographic PDF Verification*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Form Filling & E-Signature Tools**. These tools let teams prepare PDFs with fillable fields, send them for signature, track completion, and store legally binding signed documents — with a spectrum running from polished commercial suites like DocuSign and PandaDoc to self-hosted platforms that keep signed contracts on your own infrastructure.

**Examples** include DocuSeal, Documenso, OpenSign, and LibreSign (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, cryptographic PDF signing, and transparent audit trails — especially relevant as **DocuSeal** adds AI-powered field detection while remaining AGPL-licensed , and **Documenso** offers a modern Next.js stack with per-envelope pricing eliminated .

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **DocuSign** — **The reference commercial e-signature standard.** Legally binding signatures, templates, bulk send, and enterprise integrations. **Subscription-based** per-envelope or per-seat. **Trade-offs**: per-envelope pricing scales with volume, and documents live on DocuSign's infrastructure . **Best for enterprises** needing the most mature compliance and integration ecosystem, accepting subscription costs.

- **Adobe Fill & Sign** — **Adobe's mobile form-filling and signature app.** Fill forms, add signatures, and share PDFs from mobile devices. **Free with Adobe account**. **Best for Adobe users** needing simple mobile form filling without a full e-signature workflow .

- **PandaDoc** — **The document automation and e-signature platform.** Templates, proposals, quotes, and e-signatures with CRM integrations. **Subscription-based**. **Best for sales teams** wanting document generation and signing in one workflow .

- **SignNow** — **The affordable commercial e-signature platform.** Templates, bulk invites, and mobile signing. **Subscription-based** per-user. **Best for small teams** wanting a DocuSign alternative at lower cost.

## Open-Source GitHub Projects

- **DocuSeal** — **The most feature-complete open-source DocuSign alternative.** **AGPL-3.0 licensed**, self-hosted via Docker in minutes with SQLite by default (PostgreSQL/MySQL optional) . **WYSIWYG PDF form builder** with **12 field types** (signature, date, file, checkbox, and more), **multiple signers per document**, automated SMTP emails, and **cryptographic PDF eSignature with verification** . **DocuSeal 2.3.0** added **AI-powered field detection** that automatically identifies form fields in PDF documents, plus a new Select mode for moving/scaling/configuring multiple fields at once . **Storage options**: local disk, AWS S3, Google Cloud Storage, or Azure Blob . **Pro features** include white-labeling, user roles, reminders, SMS verification, conditional fields, bulk send via CSV/XLSX, and SAML SSO . **SOC 2 and ISO 27001 certified** . **The honest caveat**: **self-hosted instances generate their own signing certificate by default** — signed PDFs will not show as "verified" in Adobe Reader unless you supply a CA-issued certificate . **Best for teams** wanting a production-ready, self-hosted e-signature platform with AI field detection and broad storage support.

- **Documenso** — **The transparent open-source DocuSign alternative built on modern web stack.** **AGPL-3.0 licensed**, **v2.9.0**, built with **Next.js, PostgreSQL, and Prisma** . **Drag-and-drop signature field placement** on any PDF, **multi-recipient signing flows** with sequential or parallel ordering, and **cryptographic PDF signing** using a local `.p12` certificate with optional **RFC 3161 timestamp authority** . **Full audit trail** — who signed, when, from which IP — plus REST API and webhooks for CRM integration . **OAuth via Google, Microsoft, and generic OIDC** . **Custom branded signing experiences per team** . **Deployment via Railway** with managed PostgreSQL and auto-generated HTTPS domain . **The honest caveat**: **auto-generated self-signed certificate by default** — replace with a CA-issued certificate for verified PDFs in Adobe Reader . **Best for teams** wanting a clean, modern self-hosted signing platform with a developer-friendly API and transparent architecture.

- **OpenSign** — **The free and open-source DocuSign alternative.** **AGPL-3.0 licensed**, with **secure PDF e-signing**, annotation tools (hand-drawn, uploaded, typed, or saved signatures), **multi-signer support** with sequencing, **email OTP verification for guest signers**, and **expiring documents** with rejection reasons . **PDF template creation**, **OpenSign Drive** for document storage, **audit trails with completion certificates**, REST API, and **Zapier integration** . **Docker deployment** via a single command . **The honest caveat**: **default MongoDB instance is not persistent** — data clears on restart unless you configure your own MongoDB connection URL . **Best for teams** wanting a feature-rich open-source signing platform with OTP verification and template management, accepting the MongoDB persistence caveat.

- **LibreSign** — **The Nextcloud-integrated open-source e-signature platform.** **AGPL-3.0 licensed**, **recognized as a Digital Public Good** by the Digital Public Goods Alliance . **Requires Nextcloud to run** — it is not a standalone application . **Supports SES, AES, and QES workflows**, with **sequential signing**, multi-signer workflows, and **external signers via secure link without an account** . **Cryptographic hash for each signed document** ensures tamper detection, with timestamps for every signature . **No monthly limit on documents or signatures** . **REST API** for system integration, and **European hosting options** for GDPR/data residency . **The honest caveat**: **Nextcloud dependency** — if you do not already run Nextcloud, LibreSign requires that infrastructure first . **Best for organizations** already using Nextcloud and wanting an open-source, auditable e-signature workflow with Digital Public Good recognition.

### Additional Strong Open-Source Options

- **SuiteOp Sign** — **The white-labeled Documenso fork.** **AGPL-3.0 licensed** (inherited from Documenso), based on **Documenso v1.13.1**, with custom branding, updated logos, and white-labeled email templates . **Same core features**: electronic signatures, smart templates, team collaboration, API access, and self-hosting . **Docker deployment** with PostgreSQL and S3-compatible storage . **Best for teams** wanting Documenso's foundation with pre-applied branding, accepting that it tracks an older Documenso version .

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Form filling and e-signature tools differ significantly in deployment model, signing certificate handling, and feature depth. **DocuSeal and Documenso both generate self-signed certificates by default** — signed PDFs will not display as "verified" in Adobe Reader unless you supply a CA-issued certificate . **DocuSeal's AI field detection requires version 2.3.0+** and is accessed via right-click context menu . **Documenso uses PostgreSQL** and requires proper database setup for production . **OpenSign's default MongoDB is non-persistent** — data clears on restart without external MongoDB configuration . **LibreSign requires Nextcloud** — it is not a standalone signing server . **Qualified electronic signatures (QES)** under eIDAS require a qualified certificate and trust service setup that open-source tools alone do not provide .
- Self-hosted open-source solutions require proper certificate management (CA-issued for verified PDFs), database configuration (PostgreSQL for Documenso, SQLite/PostgreSQL for DocuSeal), and awareness that "free" self-hosted still has infrastructure and maintenance costs.

---

**Made for legal teams, HR departments, sales operations, and developers choosing form filling and e-signature tools that match their compliance needs and data-ownership requirements.**
Let's make form filling and e-signature more open, self-hostable, and legally transparent.
