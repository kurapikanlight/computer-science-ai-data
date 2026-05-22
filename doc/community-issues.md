# Community Epics — flagship issues to rally contributors

Big, ambitious initiatives for students and the community. Each is an **epic**
(a vision + scope), meant to be broken into smaller `good first issue` tasks as
people sign up. Drawn from the project roadmap (AI assistant, agent, learning
formats, integrations).

Labels suggested per epic: `epic`, plus `help wanted`, and area labels
(`web`, `ai`, `backend`, `content`).

---

## 1. 🧭 Methodology Master — an AI agent that mentors researchers

**Vision:** A conversational **agent** that walks a researcher through a chosen
methodology end to end — asking the right questions at each step, critiquing
drafts, suggesting next actions, and producing artifacts (research questions,
protocol outline, related-work table, reproducibility checklist).

**Why it matters:** This is the project's flagship — it turns a static guide
into an active mentor. Aligns with the "AI assistant (MCP + skills)" roadmap.

**Scope / sub-tasks:**
- [ ] Define the agent's capabilities and guardrails (mentor, not ghostwriter)
- [ ] Ground the agent in the existing methodology content (`web/src/guide/methodologies/`)
- [ ] Per-step prompting: given the user's current step, ask targeted questions
- [ ] Tooling via **MCP** (e.g. fetch references, generate a protocol template, lint a research question)
- [ ] Powered by Claude (latest model); streaming responses in the web app
- [ ] Persist a "research project" the agent and user build together

**Suggested stack:** Anthropic Claude API + MCP server (the future `api/`),
React chat UI. **Good for:** AI/agent-curious students, prompt engineers.
**Difficulty:** Large.

---

## 2. 💬 Research Methodology Chatbot (grounded Q&A assistant)

**Vision:** An embedded chatbot that answers "how do I…?" methodology questions,
**grounded in the guide content** (retrieval over the methodologies, with
citations back to the relevant step) so answers are accurate, not hallucinated.

**Scope / sub-tasks:**
- [ ] Chunk + index the methodology content (RAG)
- [ ] Retrieval + answer with inline citations linking to `/guide/<id>` steps
- [ ] Chat widget in the web app (Méridien-styled)
- [ ] "I don't know / see the guide" fallback when off-topic
- [ ] Evaluation set of Q&A pairs to measure answer quality

**Suggested stack:** Claude API, a vector store, the `api/` backend.
**Good for:** students into NLP/RAG, frontend devs. **Difficulty:** Large.

---

## 3. 🧪 "Which methodology should I use?" — decision-aid wizard

**Vision:** A guided questionnaire that recommends a methodology and research
design (quantitative / qualitative / mixed / R&D; or a discipline guide) based
on the user's goal, data, and constraints — an "outils d'aide à la décision".

**Scope / sub-tasks:**
- [ ] Design the decision tree / question flow
- [ ] Map answers → recommended methodology + rationale
- [ ] Result page linking into the matching guide
- [ ] Shareable result

**Good for:** students who like UX + logic, no AI required. **Difficulty:** Medium-Large.

---

## 4. 🎯 Adaptive quizzes & self-assessment per step

**Vision:** Each methodology step gets a short quiz so learners can test
understanding; optionally **AI-generated** questions from the step content,
with explanations.

**Scope / sub-tasks:**
- [ ] Quiz data model + UI (MCQ, short answer)
- [ ] Author quizzes for the CS-AI guide, or generate from content
- [ ] Track progress per methodology
- [ ] Score + explanations

**Good for:** education-minded students, frontend devs. **Difficulty:** Medium.

---

## 5. ⚙️ Backend API + AI service (the `api/` foundation)

**Vision:** Stand up the `api/` service that powers the agent, chatbot, auth,
and persisted projects — the backbone for epics 1, 2, 4.

**Scope / sub-tasks:**
- [ ] Choose & document the stack (Node.js is currently "under evaluation")
- [ ] Project skeleton, env config, CI job
- [ ] Claude API proxy with streaming + rate limiting
- [ ] Content/RAG endpoints
- [ ] Auth + persistence (optional, phase 2)

**Good for:** backend students, infra-minded contributors. **Difficulty:** Large.

---

## 6. 🎬 Interactive learning formats

**Vision:** Turn each methodology into multiple formats — **infographics, case
studies, slide decks, short video/comic summaries** — so learners can pick how
they study (from the roadmap's learning formats).

**Scope / sub-tasks:**
- [ ] Infographic of the 7-step lifecycle per methodology
- [ ] One worked **case study** end to end
- [ ] Auto-generated slide deck from a guide
- [ ] (Stretch) short explainer video / comic script

**Good for:** designers, science communicators, students. **Difficulty:** Medium.

---

## Future epics (parking lot)
- 📱 **Mobile app** (Expo / React Native) reading the same guides
- 🔗 **Integrations**: export a project to **Notion**, open templates in **Google Colab**
- 🌍 **Internationalization (i18n)** — French first
- 📦 **Reproducibility toolkit**: downloadable templates (preregistration, dataset cards, model cards, repro checklists)
