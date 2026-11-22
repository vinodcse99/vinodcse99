# QA & AI Quality Engineering Portfolio — Project Status

**Owner:** Vinod Kumar Gogula  
**Last reviewed:** 22 November 2026

## Portfolio at a glance

**We are actively developing and validating exactly 3 portfolio projects.**

| # | Official project | Repository | Focus | Current status |
|---|---|---|---|---|
| 1 | AI Quality Engineering Workbench | [GitHub](https://github.com/vinodcse99/ai-quality-engineering-workbench) | LLM, RAG, agentic AI and AI security evaluation | Active — validation expanding |
| 2 | AI-Powered QA Automation Workbench | [GitHub](https://github.com/vinodcse99/ai-powered-qa-automation-workbench) | AI-assisted test design and Playwright automation | Active — core workflow demonstrated |
| 3 | Healthcare AI Testing | [GitHub](https://github.com/vinodcse99/healthcare-ai-testing) | Healthcare UI/API automation and human-reviewed AI test drafting | Active — prototype validation pending |

This is the single source of truth for the three active portfolio projects.

## Evidence rules

- **Implemented / present:** code or configuration is present in the repository.
- **Recorded result:** a test result documented in project records; it is not necessarily a fresh run during this review.
- **Freshly verified:** tests were executed and evidence captured in the current validation cycle.
- **Pending:** implementation, validation or evidence is still required.
- Do not claim production deployment, exhaustive security coverage, customer adoption or measured ROI without evidence.
- A provider name is not a foundation-model count. Claim model comparisons only after naming, running and comparing specific model IDs.
- Keep API keys and secrets out of GitHub. Use environment variables and GitHub Actions secrets.

---

# 1. AI Quality Engineering Workbench

**Repository:** https://github.com/vinodcse99/ai-quality-engineering-workbench  
**Role:** Flagship AI application quality evaluation project  
**Status:** Active — validation expanding

### Problem and objective

Traditional UI/API automation does not fully measure AI application behavior. LLMs may return incorrect or irrelevant answers; RAG systems may retrieve unsuitable context or generate unsupported answers; agents may choose incorrect tools or arguments; prompt injection may influence model behavior or expose sensitive data.

The objective is to build a reusable Python-based quality workbench for evaluating LLM response quality, RAG behavior, agentic workflows and synthetic AI security scenarios.

### Solution workflow

AI application/model output → evaluation datasets → deterministic and model-backed evaluators → Pytest execution → JSON/HTML reports → Streamlit dashboard.

### Technology and provider

| Area | Technology |
|---|---|
| Language / test runner | Python 3.12, Pytest |
| AI evaluation framework | DeepEval |
| Live provider integration | Google Gemini via google-genai |
| Evaluation datasets | JSON |
| Dashboard / charts | Streamlit, Plotly |
| Reporting | pytest-html, pytest-json-report |

Google Gemini is the documented live provider integration. DeepEval is an evaluation framework, not a foundation model. The exact Gemini model ID and completed multi-model comparison are not established by current documentation.

### Implemented / documented capabilities

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

### Recorded validation evidence

| Evidence | Recorded result |
|---|---:|
| Offline tests collected | 124 |
| Offline tests passed | 123 |
| Offline tests skipped | 1 |
| Offline tests failed | 0 |
| Gemini integration smoke test | 1/1 passed |
| Live semantic RAG evaluation | Incomplete; provider returned temporary HTTP 503 |

These are historical recorded results, not a fresh execution in this review. The incomplete RAG attempt is not a passing result. Synthetic security scenarios are not proof of a real compromise or a professional penetration test.

### Pending work

| Priority | Work | Completion evidence required |
|---|---|---|
| P0 | Fresh full offline suite | Dated report with exact pass/fail/skip counts |
| P0 | Complete live Gemini-backed RAG evaluation | Reproducible successful run with inputs, metrics and report |
| P0 | Populate agentic datasets | Positive, negative and edge cases with expected outcomes |
| P1 | Provider timeout, retry and error handling | Failure-path tests |
| P1 | Verify dashboard against latest reports | Dashboard showing current run and metrics |
| P1 | CI quality gates | Successful GitHub Actions run |
| P2 | Multi-model comparison | Named model IDs and comparable results |
| P2 | Public demo and architecture guide | Reproducible walkthrough and sample report |

**Portfolio message:** A Python/Pytest workbench for evaluating LLM, RAG, agentic workflow and synthetic AI security behavior, with Gemini integration and reporting. Live RAG validation and broader model comparison remain in progress.

---

# 2. AI-Powered QA Automation Workbench

**Repository:** https://github.com/vinodcse99/ai-powered-qa-automation-workbench  
**Role:** Flagship AI-assisted test engineering project  
**Status:** Active — core workflow demonstrated

### Problem and objective

Converting business requirements into test scenarios and automation takes significant manual effort. AI can accelerate this work, but generated tests may have invalid locators, weak assertions, missing coverage or broken traceability.

The objective is to demonstrate AI-assisted test design and Playwright automation while retaining static validation, human review, reusable Page Object Model architecture and deterministic browser assertions.

### Solution workflow

Business requirement → Gemini-assisted scenario design → structured JSON → Gemini-assisted Playwright generation → static quality gate → human review → Playwright execution → reports.

### Technology and provider

| Area | Technology |
|---|---|
| Languages / runtime | TypeScript, JavaScript, Node.js |
| UI/API automation | Playwright |
| AI provider / SDK | Google Gemini, @google/genai |
| Design pattern | Page Object Model |
| Scenario data | JSON |
| CI/CD | GitHub Actions |

Google Gemini is the documented provider. The exact model ID and multi-model comparison are not established by current documentation.

### Implemented / documented capabilities

| Capability | Status |
|---|---|
| Sample Enterprise Data Catalog application | Implemented |
| Playwright TypeScript framework and POM | Implemented |
| UI, API and service-health tests | Implemented |
| Gemini AI Test Designer | Code present; standalone end-to-end verification pending |
| Gemini-assisted automation generator | Implemented and exercised |
| Generated-test static quality gate | Implemented |
| POM, assertion, syntax and traceability checks | Implemented |
| Human review step | Documented |
| AI failure analysis | Planned |
| AI test-data assistant | Planned |
| LLM quality evaluator | Planned |
| MCP-based QA agent | Planned |

### Recorded validation evidence

| Evidence | Recorded result |
|---|---:|
| Generated Chromium suite 1 | 8 passed |
| Generated Chromium suite 2 | 10 passed |
| Total generated browser tests | 18 passed, 0 failed |
| Static quality checks | 10/10 per suite |
| TypeScript typecheck | Passed |

These are historical README-recorded results, not a fresh run during this review.

### Pending work

| Priority | Work | Completion evidence required |
|---|---|---|
| P0 | Verify standalone AI Test Designer | Requirement input → scenarios → validation report |
| P0 | Fresh standard and generated test runs | Dated Playwright reports |
| P0 | Demonstrate rejection of poor generated tests | Negative examples rejected by quality gate |
| P1 | AI failure analysis | Reproducible failure and useful diagnosis |
| P1 | Generated-test quality evaluation | Measured usefulness, correctness and traceability |
| P1 | Requirement-to-test traceability | Requirement IDs mapped to generated and executed tests |
| P2 | AI test-data assistant | Validated synthetic data generation |
| P2 | MCP QA agent | Controlled tool use with permissions and audit evidence |

**Portfolio message:** A Gemini-assisted Playwright TypeScript workflow for test design and automation generation, with static quality gates, POM reuse, traceability and recorded generated Chromium execution. Human review and deterministic assertions remain in control.

---

# 3. Healthcare AI Testing

**Repository:** https://github.com/vinodcse99/healthcare-ai-testing  
**Role:** Supporting domain QA project  
**Status:** Active — prototype validation pending

### Problem and objective

Healthcare portals need reliable login, appointment and claims workflows. Teams need UI/API validation while protecting sensitive patient information. AI-generated test drafts must be reviewed before acceptance.

The objective is to demonstrate QA automation for a synthetic clinic portal and an experimental human-reviewed AI test-drafting workflow without using real patient data.

### Solution workflow

Manual test cases (CSV) → Python AI draft generator → generated drafts → human review → accepted tests → Playwright execution → CI and reporting.

### Technology and provider

| Area | Technology |
|---|---|
| UI/API automation | Playwright |
| Automation language | TypeScript |
| Sample application | Node.js / Express |
| AI test drafting | Python |
| AI provider / SDK | Anthropic API, Python anthropic package |
| Test data / review | CSV |
| CI/CD / reporting | GitHub Actions, Playwright HTML, Python report script |

Anthropic is the documented provider. Exact model ID and successful live generation evidence are not established by current documentation. The Python SDK is installed separately from the Node package manifest.

### Implemented / documented capabilities

| Capability | Status |
|---|---|
| Synthetic clinic portal | Present |
| Login and appointment workflows | Present |
| Page objects and saved authentication state | Present / documented |
| UI tests and claims API tests | Present |
| Smoke and regression organization | Documented |
| Python AI test generator | Present |
| Manual test-case CSV | Present |
| Human review log and summary script | Present |
| GitHub Actions workflow | Present |
| Cross-browser configuration | Documented; execution not established |

### Pending work

| Priority | Work | Completion evidence required |
|---|---|---|
| P0 | Run full Playwright suite | Dated pass/fail/skip report |
| P0 | Verify GitHub Actions | Successful workflow and job results |
| P0 | Execute AI generator | Actual provider-backed generated drafts |
| P0 | Validate generated test code | Accepted and rejected examples |
| P1 | Measure review outcomes | Generated/accepted/edited/rejected counts |
| P1 | Add reports and screenshots | Public demo evidence |
| P1 | Expand API negative and boundary coverage | Reproducible tests |
| P2 | Expand synthetic healthcare workflows | Additional safe domain scenarios |

**Portfolio message:** A synthetic healthcare QA project combining Playwright UI/API automation with an experimental human-reviewed AI test-drafting workflow. It remains a supporting project until execution and AI generation evidence are published.

---

# Delivery order

1. **AI Quality Engineering Workbench:** fresh offline run, live RAG evaluation, agentic datasets, CI and dashboard evidence.
2. **AI-Powered QA Automation Workbench:** standalone Test Designer, negative quality-gate tests, fresh execution and a clear demo.
3. **Healthcare AI Testing:** UI/API execution, provider-backed draft generation and review metrics.

No new portfolio projects will be started until these three have clear, reproducible evidence.

## Professional positioning

- 14+ years in QA, software testing, automation engineering and enterprise delivery.
- Senior-level experience in test strategy, framework architecture, SDLC/STLC, UI/API testing, release quality and cross-functional delivery.
- Applying established QA engineering experience to AI quality engineering, LLM evaluation, RAG, agentic workflows and AI-assisted automation.

Do not describe this as 14 years of AI experience.
