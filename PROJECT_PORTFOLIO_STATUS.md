# Portfolio Project Status & Delivery Tracker

**Owner:** Vinod Kumar Gogula  
**Last reviewed:** 22 November 2026  
**Purpose:** One authoritative inventory of the distinct QA / AI-testing projects in this portfolio. A sample application or feature inside a project is not counted as another project.

## Portfolio at a glance

**Total distinct projects: 4**

| # | Official project | Repository | Current status |
|---|---|---|---|
| 1 | AI Quality Engineering Workbench | [GitHub](https://github.com/vinodcse99/ai-quality-engineering-workbench) | Active – initial release; validation expanding |
| 2 | AI-Powered QA Automation Workbench | [GitHub](https://github.com/vinodcse99/ai-powered-qa-automation-workbench) | Active – core workflow demonstrated |
| 3 | Healthcare AI Testing | [GitHub](https://github.com/vinodcse99/healthcare-ai-testing) | Prototype – execution evidence pending |
| 4 | Playwright ChatGPT POC | [GitHub](https://github.com/vinodcse99/playwright-chatgpt-poc) | Early scaffold – not a completed POC |

**Important naming decision:** Enterprise Data Catalog QA is NOT a separate portfolio project. The Enterprise Data Catalog is the sample application inside **AI-Powered QA Automation Workbench**. Its separate empty repository is not part of the project count and must not be featured or linked as a project.

> Status labels distinguish code presence from verified execution. Test results below are historical recorded runs, not a claim that tests were rerun on this review date.

## 1. AI Quality Engineering Workbench

**Repository:** https://github.com/vinodcse99/ai-quality-engineering-workbench

**Problem being solved**
- Conventional functional automation does not fully measure generated-answer quality.
- RAG systems can retrieve irrelevant context or produce unsupported answers.
- Agents can select the wrong tool, provide invalid arguments or execute workflows incorrectly.
- Prompt injection and sensitive-data leakage require dedicated regression scenarios.

**Solution**
A Python 3.12 / Pytest workbench with structured evaluation datasets, LLM and RAG evaluators, agent workflow modules, security scenarios, optional Gemini integration, reporting and a Streamlit dashboard.

**Implemented / recorded evidence**
- Project structure, configuration, environment template and README.
- LLM and RAG datasets and evaluator modules.
- Agentic tool-selection, tool-execution, workflow and trace-evaluation modules.
- Security evaluation runner and synthetic security scenarios.
- Streamlit dashboard.
- Recorded offline test run: 124 collected, 123 passed, 1 skipped, 0 failed.
- Recorded live Gemini integration smoke test: 1/1 passed.

**Pending**
- Complete a repeatable live semantic RAG evaluation. A prior attempt was incomplete after a provider 503 response; it is not a passing result.
- Populate currently empty agentic JSON datasets with meaningful positive, negative and edge cases.
- Expand provider retry/error handling.
- Add/verify CI quality gates.
- Rerun the full suite and publish fresh, dated evidence.

**Current assessment:** Substantial published implementation with recorded offline and Gemini smoke-test evidence. Active project; not yet a fully validated AI evaluation product.

## 2. AI-Powered QA Automation Workbench

**Repository:** https://github.com/vinodcse99/ai-powered-qa-automation-workbench

**Problem being solved**
- Converting requirements into test cases and automation scripts is repetitive.
- AI-generated tests may contain invalid locators, weak assertions or missing requirement traceability.
- Teams need quality controls before generated code is executed.

**Solution**
A Gemini-assisted test-design and Playwright TypeScript generation workflow using Page Object Model reuse, structured scenarios, static quality checks, human review and deterministic browser execution.

**Implemented / recorded evidence**
- Sample Enterprise Data Catalog application with search, filters and asset details.
- Playwright TypeScript framework and POM.
- UI, API and service-health coverage.
- AI test-design and automation-generation components.
- Generated-test static quality gate and workflow runner.
- Recorded generated browser execution: 18 passed, 0 failed.
- Both generated suites recorded 10/10 static quality checks; TypeScript typecheck passed.

**Pending**
- Independently verify the standalone AI Test Designer end-to-end.
- Demonstrate rejection of poor AI-generated tests.
- Add failure analysis and AI-generated test quality evaluation.
- Keep planned features (test-data assistant, LLM evaluator and MCP QA agent) labelled as planned until implemented and verified.

**Current assessment:** Working AI-assisted test-generation demonstration with static validation and recorded Chromium execution. The Enterprise Data Catalog is a demonstrator within this project, not a separate project.

## 3. Healthcare AI Testing

**Repository:** https://github.com/vinodcse99/healthcare-ai-testing

**Problem being solved**
Demonstrate safe testing of synthetic healthcare workflows and human-reviewed AI-generated test drafts without using real patient data.

**Solution**
A sample Express clinic portal with Playwright UI/API automation, page objects, Python-based AI test draft generation and a review log/report workflow.

**Implemented / present in repository**
- Sample app, login and appointment page objects.
- Login and appointment tests, claims API tests.
- Manual test-case CSV.
- AI test-generation and review-report scripts.
- Playwright configuration and CI workflow.

**Pending**
- Run the suite locally and through GitHub Actions; record actual pass/fail/skip counts.
- Verify AI generation against its configured provider.
- Record generated, accepted, edited and rejected draft counts.
- Expand synthetic workflow and negative/API coverage.
- Update README with actual evidence.

**Current assessment:** Prototype with implementation present; end-to-end execution and AI workflow evidence pending.

## 4. Playwright ChatGPT POC

**Repository:** https://github.com/vinodcse99/playwright-chatgpt-poc

**Problem / intended direction**
Explore a small proof of concept combining Playwright automation with a ChatGPT-related interaction.

**Present in repository**
- Playwright Test dependency and configuration.
- GitHub Actions workflow configuration.

**Pending**
- Define the exact use case (ChatGPT UI automation or API-assisted test workflow).
- Implement the integration and meaningful test assertions.
- Keep credentials in environment secrets.
- Add reproducible setup instructions and execution evidence.

**Current assessment:** Early scaffold only. Do not present it as a completed integration.

## Delivery order

1. Finish and validate the AI Quality Engineering Workbench.
2. Finish the end-to-end verification and demo of the AI-Powered QA Automation Workbench.
3. Validate the existing Healthcare AI Testing prototype.
4. Keep the Playwright ChatGPT POC frozen until there is a clear job-relevant reason to complete it.

## Portfolio reporting rules

- **Implemented** means code exists.
- **Verified** means execution evidence exists.
- **In progress** means a workflow is partially implemented or not fully validated.
- **Planned** means it is not yet built.
- Date and identify each test run; distinguish offline tests from live-provider tests.
- Do not claim production deployment based on independent sample projects.
- Do not count sample applications, modules or features as separate portfolio projects.
