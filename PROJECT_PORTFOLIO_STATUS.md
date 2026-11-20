# Portfolio Project Status & Delivery Tracker

**Owner:** Vinod Kumar Gogula  
**Last reviewed:** 20 November 2026  
**Purpose:** A transparent record of each public QA / AI-testing portfolio project: why it exists, what it demonstrates, verified outputs, current maturity, and remaining work.

> Status labels describe the evidence currently present in the public repositories and recent project work. A repository containing code or a configured workflow is not automatically considered complete. Test results are snapshots from recorded runs, not guarantees of future runs.

## Portfolio at a glance

| Project | Goal | Current status | Verified output / evidence | Main pending work |
|---|---|---|---|---|
| [AI Quality Engineering Workbench](https://github.com/vinodcse99/ai-quality-engineering-workbench) | Test quality, reliability, RAG, agentic workflows and security behavior of AI applications | **Active – initial public release; validation expanding** | README records 124 collected offline tests (123 passed, 1 skipped); Gemini integration smoke test 1/1 passed. | Complete repeatable semantic RAG evaluation; populate remaining agentic datasets; expand provider resilience and CI. |
| [AI-Powered QA Automation Workbench](https://github.com/vinodcse99/ai-powered-qa-automation-workbench) | Use GenAI to draft test scenarios and Playwright automation with static gates and deterministic execution | **Active – core workflow demonstrated** | 18/18 generated Chromium browser tests passed in the recorded run; both generated suites passed 10/10 static quality checks; TypeScript typecheck passed. | Independently verify standalone AI Test Designer end-to-end; add failure analysis, test-data assistant, LLM evaluation and MCP integration. |
| [Healthcare AI Testing](https://github.com/vinodcse99/healthcare-ai-testing) | Demonstrate UI/API automation and human-reviewed AI-generated tests for a sample clinic portal | **Prototype – implementation present; end-to-end evidence pending** | Sample Express app, Playwright login/appointment tests, claims API tests, page objects, AI draft generator and CI workflow are present. | Run and record local/CI results; validate AI generation and review workflow; add measured results and broaden clinical workflow coverage. |
| [Playwright ChatGPT POC](https://github.com/vinodcse99/playwright-chatgpt-poc) | Explore a small proof of concept connecting ChatGPT-related capability with Playwright | **Early scaffold – not a completed POC yet** | Repository has Playwright dependency, config and a CI workflow. | Define the exact integration use case; add implementation, test cases, safe API-key handling, execution evidence and README instructions. |
| Enterprise Data Catalog QA sample | Demonstrate enterprise catalog search, filtering, asset details and generated automation | **Demonstrator is part of the AI-Powered QA Automation Workbench; separate repo is empty** | The AI-Powered QA Automation Workbench README documents a sample catalog app and UI/API/service coverage, with 18 generated browser tests passing in a recorded run. | Keep the sample project documented under the AI-Powered QA Automation Workbench, or populate the empty standalone repository before linking it as a separate project. |

## 1. AI Quality Engineering Workbench

**Repository:** https://github.com/vinodcse99/ai-quality-engineering-workbench  
**Purpose / why it was started:** Build a practical quality-engineering workbench for evaluating AI-enabled applications, rather than limiting QA to conventional UI/API automation. The project explores repeatable evaluation of LLM responses, RAG behavior, agentic tool workflows and AI security scenarios.

**Problem being addressed**
- Traditional functional automation does not fully measure the quality of generated answers.
- RAG systems can retrieve irrelevant context or produce unsupported answers.
- Agentic workflows can select the wrong tool, provide invalid arguments or execute actions in the wrong sequence.
- Prompt injection and sensitive-data leakage require dedicated regression scenarios.

**Approach / solution**
- Python 3.12 and Pytest-based test architecture.
- Structured JSON datasets for LLM, RAG, agentic and security cases.
- Deterministic evaluators and optional model-backed Gemini / DeepEval experiments.
- Agent modules for tool selection, argument validation, execution and trace evaluation.
- Streamlit dashboard and JSON/HTML-oriented reporting.

**Implemented / evidenced**
- Project structure, requirements, environment template and README published.
- LLM and RAG datasets and evaluator modules are present.
- Agentic tool-selection, tool-execution, workflow and trace-evaluation modules are present.
- Security evaluation runner and synthetic security scenarios are present.
- Streamlit dashboard is present.
- The published README records an offline run of 124 collected tests: 123 passed, 1 skipped, 0 failed.
- A live Gemini integration smoke test passed 1/1 in the recorded run.

**Known limitations / pending**
- A semantic RAG model-backed evaluation attempt was incomplete after a temporary provider 503 response; it must not be reported as a passing evaluation.
- Several agentic JSON dataset files in the published tree are currently empty and need meaningful cases.
- Expand repeatable model-backed evaluation, provider retry/error handling and evaluation evidence.
- Add CI automation and publish a reproducible validation snapshot after rerunning the full suite.
- Continue documenting evaluator thresholds, limitations and human-review requirements.

**Current output:** A published Python/Pytest workbench with evaluation modules, datasets, security scenarios, a dashboard and recorded offline/Gemini smoke-test evidence. This is an active portfolio project, not a certified or exhaustive AI safety assessment.

## 2. AI-Powered QA Automation Workbench

**Repository:** https://github.com/vinodcse99/ai-powered-qa-automation-workbench  
**Purpose / why it was started:** Demonstrate how Generative AI can reduce repetitive QA effort by converting business requirements into candidate scenarios and Playwright tests, while keeping quality decisions deterministic and human-reviewed.

**Problem being addressed**
- Manual conversion of requirements into test cases is time-consuming.
- Automation scripts require repeated implementation and maintenance.
- AI-generated code can contain invalid locators, weak assertions or tests that do not trace to requirements.

**Approach / solution**
- Google Gemini-assisted test design and Playwright TypeScript generation.
- Existing Page Object Model reuse.
- Structured scenario JSON and generated TypeScript tests.
- Static quality gate for syntax, imports, POM usage, assertions, uniqueness and scenario traceability.
- Human review followed by deterministic Playwright execution.

**Implemented / evidenced**
- Sample Enterprise Data Catalog application with search, filters and asset details.
- Playwright TypeScript framework and POM.
- UI, API and service-health test coverage.
- AI test-design and automation-generation components.
- Generated-test static quality gate and workflow runner.
- Recorded generated browser execution: 18 tests passed, 0 failed.
- Both generated suites recorded 10/10 static quality checks; TypeScript typecheck passed.
- Rejected generated outputs and run reports are kept separately for traceability.

**Known limitations / pending**
- Standalone AI Test Designer end-to-end execution is not independently verified.
- AI-generated tests still require human review.
- AI failure analyzer, AI test-data assistant, LLM evaluator and MCP-based QA agent are roadmap items.
- Greenfield generation of an entire framework is not implemented.
- Recorded browser evidence covers the sample application and Chromium suites, not production applications or broad cross-browser certification.

**Current output:** A working AI-assisted scenario-to-Playwright-generation demonstration with static quality validation and a recorded 18/18 Chromium execution.

## 3. Healthcare AI Testing

**Repository:** https://github.com/vinodcse99/healthcare-ai-testing  
**Purpose / why it was started:** Create a safe, synthetic healthcare/clinic portal to demonstrate practical UI and API testing, authentication, appointment workflows and human-reviewed AI-assisted test generation without using real patient information.

**Problem being addressed**
- Healthcare workflows require validation across authentication, appointments and claims.
- AI-generated automation needs review and measurable acceptance rather than blind execution.
- Test data must remain synthetic and must not expose patient information.

**Approach / solution**
- Sample Express application with in-memory data.
- Playwright and TypeScript tests using Page Object Model.
- Login/authentication setup, appointment UI scenarios and claims API tests.
- Python-based LLM draft generator and review log/report workflow.
- GitHub Actions workflow configured for pull-request smoke tests and scheduled regression.

**Implemented / evidenced in repository**
- Sample app, login and appointment page objects.
- Login tests, appointment tests and claims API tests.
- Manual test-case CSV.
- AI test-generation and review-report scripts.
- Playwright configuration and CI workflow.

**Known limitations / pending**
- The repository README does not yet publish a measured passing test run; do not describe the project as fully tested or complete.
- Execute the suite locally and through GitHub Actions, then record actual pass/fail/skip counts.
- Verify the AI generator against the configured model/provider and document accepted, edited and rejected draft counts.
- Expand realistic but synthetic workflows and negative/API coverage.
- Add evidence and update the README results section.

**Current output:** A functional-looking test project structure and sample application with automation and AI-generation components; execution and AI-workflow evidence still need to be captured.

## 4. Playwright ChatGPT POC

**Repository:** https://github.com/vinodcse99/playwright-chatgpt-poc  
**Purpose / why it was started:** Explore a small proof of concept for combining Playwright automation with a ChatGPT-related interaction.

**Current repository evidence**
- Playwright Test dependency and configuration.
- GitHub Actions workflow configured to install dependencies and run Playwright.
- No actual test specification or ChatGPT integration implementation is currently visible in the repository.
- Package scripts are empty and the README contains only a short title/description.

**Pending**
1. Define whether the POC targets ChatGPT UI automation or an API-assisted test workflow.
2. Implement the minimal end-to-end scenario and test assertions.
3. Keep API keys in environment secrets; never commit credentials.
4. Add a reproducible setup/run guide and CI result.
5. Update the README with architecture, screenshots or reports and limitations.

**Current output:** Initial Playwright repository scaffold only. It should not be presented as a completed ChatGPT integration.

## 5. Enterprise Data Catalog QA – how it fits

The GitHub repository named `enterprise-data-catalog-qa` currently has no committed files (GitHub reports the repository as empty). The sample Enterprise Data Catalog application and its automation are documented and included within the [AI-Powered QA Automation Workbench](https://github.com/vinodcse99/ai-powered-qa-automation-workbench).

Therefore:
- Feature the AI-Powered QA Automation Workbench as the repository link.
- Describe the Enterprise Data Catalog as the sample application used by that workbench.
- Do not link the empty standalone repository as a completed project.
- If a separate repository is desired later, publish the actual source and its own README, tests and execution evidence first.

## Recommended delivery order

1. **AI Quality Engineering Workbench:** complete the semantic RAG evaluation and populate agentic datasets; rerun and record the full validation.
2. **AI-Powered QA Automation Workbench:** independently verify the standalone Test Designer and implement the next highest-value capability (failure analysis).
3. **Healthcare AI Testing:** run the existing tests and CI, verify AI draft generation, then publish real test results.
4. **Playwright ChatGPT POC:** either implement the promised integration or keep it clearly labelled as an early scaffold / remove it from featured projects until it has substance.
5. **Enterprise Data Catalog:** keep it as the demonstrator inside the AI-Powered QA Automation Workbench unless the standalone repository is populated.

## Reporting rules for this portfolio

- Use **Implemented** for code that exists.
- Use **Verified** only when there is execution evidence.
- Use **In progress** for partially implemented workflows.
- Use **Planned** for roadmap items that are not yet built.
- Publish test counts with the date/run context and distinguish offline tests from live provider calls.
- Never present synthetic security test findings as evidence of a real compromise.
- Never claim production healthcare, mortgage or enterprise deployment based on these independent sample projects.
