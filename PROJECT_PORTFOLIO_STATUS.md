# QA & AI Quality Engineering Portfolio — Status

**Owner:** Vinod Kumar Gogula  
**Reviewed:** 22 November 2026  
**Purpose:** Single source of truth. Sample applications and unfinished scaffolds are not counted as finished portfolio projects.

## Portfolio at a glance

**3 projects retained: 2 flagship AI engineering projects and 1 supporting domain QA project.**

| # | Project | Repository | Role / status |
|---|---|---|---|
| 1 | AI Quality Engineering Workbench | [GitHub](https://github.com/vinodcse99/ai-quality-engineering-workbench) | Flagship 1 — active; validation expanding |
| 2 | AI-Powered QA Automation Workbench | [GitHub](https://github.com/vinodcse99/ai-powered-qa-automation-workbench) | Flagship 2 — core workflow demonstrated |
| 3 | Healthcare AI Testing | [GitHub](https://github.com/vinodcse99/healthcare-ai-testing) | Supporting project — prototype; execution evidence pending |

**Excluded:** Playwright ChatGPT POC is an early scaffold with a short README, empty npm scripts and no demonstrated ChatGPT integration or meaningful test evidence. Remove it from featured projects and archive it rather than presenting it as complete. Enterprise Data Catalog QA is the sample application inside Project 2, not a separate project; do not count or feature its separate empty repository.

## Evidence rules

- **Implemented / present** means documented or code/configuration is present.
- **Recorded result** means a README or earlier project record reports a test run; it is not a fresh run on this review date.
- This review inspected the four repository READMEs and selected dependency manifests. It did not run local tests or inspect every source file.
- A provider name is not a foundation-model count. Claim model comparisons only after naming, running and comparing specific model IDs.
- Do not claim production deployment, exhaustive security coverage, customer adoption or measured ROI without evidence.

---

# 1. AI Quality Engineering Workbench

**Repository:** https://github.com/vinodcse99/ai-quality-engineering-workbench  
**Role:** Main AI application quality evaluation showcase  
**Status:** Active; validation expanding

### Problem

Traditional UI/API automation does not fully measure AI application behavior. LLMs may return incorrect or irrelevant answers; RAG systems may retrieve unsuitable context or generate unsupported answers; agents may choose incorrect tools or arguments; prompt injection may influence model behavior or expose sensitive data. Teams need repeatable evaluation scenarios and regression evidence.

### Objective and solution

Build a Python-based quality workbench to evaluate LLM response quality, RAG behavior, agentic workflows and synthetic AI security scenarios. Workflow: datasets → evaluators → Pytest → JSON/HTML reports → Streamlit dashboard.

### Technology and providers

| Area | Technology |
|---|---|
| Language / test runner | Python 3.12, Pytest |
| AI evaluation | DeepEval |
| Live provider | Google Gemini via google-genai |
| Data | JSON evaluation datasets |
| Dashboard / charts | Streamlit, Plotly |
| Reports | pytest-html, pytest-json-report |

**Provider/model clarity:** Gemini is the one documented live provider integration. DeepEval is an evaluation framework, not a model. The README does not establish the exact Gemini model ID or a completed multi-model comparison.

### Implemented / present in repository documentation

| Capability | Status |
|---|---|
| Python/Pytest framework | Implemented |
| LLM evaluation utilities and scenarios | Implemented |
| RAG components and scenarios | Present; live semantic evaluation incomplete |
| Agent tool-selection / argument validation | Present |
| Agent execution sequence / trace evaluation | Present |
| Synthetic direct and indirect prompt-injection scenarios | Implemented |
| Synthetic sensitive-data-leakage scenarios | Implemented |
| Gemini integration | Implemented; smoke test recorded as passed |
| Streamlit dashboard and reporting | Implemented |

### Recorded evidence

| Test evidence | Recorded result |
|---|---:|
| Offline suite | 124 collected |
| Passed / skipped / failed | 123 / 1 / 0 |
| Gemini smoke test | 1/1 passed |
| Live semantic RAG attempt | Incomplete; provider returned temporary HTTP 503 |

Historical results only, not freshly rerun in this review. Security findings are synthetic scenario results, not proof of a real compromise or a professional penetration test.

### Pending

| Priority | Work | Required evidence |
|---|---|---|
| P0 | Fresh full offline run | Dated report with pass/fail/skip counts |
| P0 | Complete live Gemini RAG evaluation | Reproducible successful run and metrics |
| P0 | Populate agentic datasets | Positive, negative and edge cases |
| P1 | Provider retries, timeouts and error handling | Failure-path tests |
| P1 | Verify dashboard with latest reports | Current-run dashboard evidence |
| P1 | CI quality gates | Successful Actions run |
| P2 | Multi-model comparison | Named model IDs and comparable results |
| P2 | Public demo | Architecture walkthrough and sample report |

**Safe portfolio claim:** A Python/Pytest workbench demonstrating LLM, RAG, agentic workflow and synthetic AI security evaluation patterns, with optional Gemini integration and reporting. Live RAG validation and model comparison remain in progress.

---

# 2. AI-Powered QA Automation Workbench

**Repository:** https://github.com/vinodcse99/ai-powered-qa-automation-workbench  
**Role:** Main AI-assisted test engineering showcase  
**Status:** Active; core generation workflow demonstrated

### Problem

Converting business requirements into test scenarios and automation takes significant manual effort. AI can accelerate this work, but generated tests may have invalid locators, weak assertions, missing coverage or broken traceability. Unreviewed generated tests can reduce quality.

### Objective and solution

Demonstrate AI-assisted test design and Playwright automation while retaining static validation, human review, POM reuse and deterministic browser assertions.

Workflow: business requirement → Gemini-assisted scenario design → structured JSON → Gemini-assisted Playwright generation → static quality gate → human review → Playwright execution → reports.

The Enterprise Data Catalog is the sample application within this project, not a separate project.

### Technology and provider

| Area | Technology |
|---|---|
| Languages / runtime | TypeScript, JavaScript, Node.js |
| Automation | Playwright |
| AI provider / SDK | Google Gemini, @google/genai |
| Design | Page Object Model |
| Data / CI | JSON, GitHub Actions |

Gemini is the one documented provider. Exact model ID and multi-model comparison are not established.

### Implemented / present according to README

| Capability | Status |
|---|---|
| Sample Enterprise Data Catalog app | Implemented |
| Playwright TypeScript framework and POM | Implemented |
| UI, API and service-health tests | Implemented |
| Gemini AI Test Designer | Code present; standalone end-to-end verification pending |
| Gemini-assisted automation generator | Implemented and exercised |
| Generated-test static quality gate | Implemented |
| POM, assertion, syntax and traceability checks | Implemented |
| Human review step | Documented |
| AI failure analysis, test-data assistant, LLM evaluator, MCP QA agent | Planned |

### Recorded evidence

| Evidence | Recorded result |
|---|---:|
| Generated Chromium suite 1 | 8 passed |
| Generated Chromium suite 2 | 10 passed |
| Total generated browser tests | 18 passed, 0 failed |
| Static checks | 10/10 per suite |
| TypeScript typecheck | Passed |

These are README-recorded results, not a fresh run during this review; they cover the sample app, not production-system coverage.

### Pending

| Priority | Work | Required evidence |
|---|---|---|
| P0 | Verify standalone AI Test Designer | Requirement input → scenarios → report |
| P0 | Fresh standard and generated test runs | Dated Playwright reports |
| P0 | Demonstrate poor-test rejection | Negative examples rejected by quality gate |
| P1 | AI failure analysis | Reproducible failure and diagnosis |
| P1 | Generated-test quality evaluation | Measured usefulness, correctness and traceability |
| P1 | Requirement-to-test traceability | Requirement IDs mapped to generated/executed tests |
| P2 | Test-data assistant and MCP QA agent | Working demos, permissions and audit evidence |

**Safe portfolio claim:** A Gemini-assisted Playwright TypeScript test engineering workflow with scenario generation, static quality gates, POM reuse and recorded generated Chromium execution. Human review and deterministic assertions remain in control.

---

# 3. Healthcare AI Testing

**Repository:** https://github.com/vinodcse99/healthcare-ai-testing  
**Role:** Supporting domain QA project  
**Status:** Prototype; execution evidence pending

### Problem

Healthcare portals need reliable login, appointment and claims workflows. Teams need UI/API validation while avoiding exposure of real patient information. AI-generated test drafts must be reviewed before acceptance.

### Objective and solution

Demonstrate QA automation for a synthetic clinic portal and an experimental human-reviewed AI test-drafting workflow.

Workflow: manual cases (CSV) → Python AI draft generator → generated drafts → human review → accepted tests → Playwright → CI/reporting.

### Technology and provider

| Area | Technology |
|---|---|
| Automation / language | Playwright, TypeScript |
| Sample application | Node.js / Express |
| AI drafting | Python |
| Provider / SDK | Anthropic API, Python anthropic package |
| Test data / review | CSV |
| CI / reporting | GitHub Actions, Playwright HTML, Python report script |

Anthropic is documented as the provider. Exact model ID and successful live generation evidence are not established. Its Python SDK is installed separately from the Node package manifest.

### Implemented / present according to README

| Capability | Status |
|---|---|
| Synthetic clinic portal | Present |
| Login and appointment workflows | Present |
| Page objects and saved authentication state | Present / documented |
| UI tests and claims API tests | Present |
| Smoke / regression organization | Documented |
| Python AI test generator | Present |
| Manual cases, review log and summary script | Present |
| GitHub Actions workflow | Present |
| Cross-browser configuration | Documented; execution not established |

### Pending

| Priority | Work | Required evidence |
|---|---|---|
| P0 | Run full Playwright suite | Dated pass/fail/skip report |
| P0 | Verify GitHub Actions | Successful workflow and job results |
| P0 | Execute AI generator | Actual provider-backed drafts |
| P0 | Validate generated tests | Accepted and rejected examples |
| P1 | Measure review outcomes | Generated/accepted/edited/rejected counts |
| P1 | Add reports and screenshots | Public demo evidence |
| P1 | Expand API negative/boundary coverage | Reproducible tests |
| P2 | Expand synthetic healthcare workflows | Additional safe domain scenarios |

**Safe portfolio claim:** A synthetic healthcare QA project combining Playwright UI/API automation with an experimental human-reviewed AI test-drafting workflow. Keep as supporting work until execution and AI evidence are published.

---

# Excluded projects and naming decisions

| Name | Decision | Reason |
|---|---|---|
| Playwright ChatGPT POC | Remove from featured portfolio; archive | No meaningful ChatGPT integration or test evidence established; npm scripts are empty |
| Enterprise Data Catalog QA | Do not count separately | Sample application inside AI-Powered QA Automation Workbench |

Do not permanently delete repositories until local copies and useful code have been checked. Archiving preserves history.

# Delivery order

1. Finish AI Quality Engineering Workbench: fresh offline run, live RAG, agentic datasets, CI and dashboard evidence.
2. Finish AI-Powered QA Automation Workbench: standalone Test Designer, negative quality-gate tests, fresh execution and demo.
3. Validate Healthcare AI Testing: UI/API execution, live draft generation and review metrics.
4. Keep ChatGPT POC excluded/archived. Do not start another project before these deliverables are complete.

## Professional positioning

- 14+ years in QA, software testing, automation engineering and enterprise delivery.
- Senior-level experience in test strategy, framework architecture, SDLC/STLC, UI/API testing, release quality and cross-functional delivery.
- Applying established QA engineering experience to AI quality engineering, LLM evaluation, RAG, agentic workflows and AI-assisted automation.

Do not describe this as 14 years of AI experience.
