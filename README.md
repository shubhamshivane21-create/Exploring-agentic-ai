# Exploring Agentic AI

*A Report on Objectives, Decision-Making, Algorithms, Industry Applications, and Ethical Considerations*

**Prepared by:** Shubham Shivane | AI Engineer Roadmap – Agentic AI Module

---

## 1. Introduction

Agentic AI refers to artificial intelligence systems that go beyond simple prediction or content generation and are capable of autonomously planning, deciding, and taking actions to achieve a defined goal. Unlike traditional AI models that respond passively to a single prompt, an agentic system can break down a task, choose appropriate tools, execute multi-step workflows, observe the results, and adjust its approach — all with minimal human intervention. This report explores the core objectives of Agentic AI, how such systems make decisions, the algorithms that power them, real-world industry applications, and the ethical considerations that must guide their development and deployment.

## 2. Objectives of Agentic AI

- **Autonomy** — enabling AI to operate with minimal step-by-step human supervision once a goal is defined.
- **Goal-oriented behaviour** — breaking a high-level objective into smaller, executable sub-tasks.
- **Tool use and integration** — allowing the agent to interact with external systems such as APIs, databases, and files to complete real-world tasks.
- **Adaptability** — adjusting plans dynamically based on feedback, errors, or new information.
- **Efficiency** — automating repetitive research, analysis, and reporting workflows that would otherwise require significant manual effort.

## 3. Decision-Making Mechanisms within AI Systems

- **Reasoning (Chain-of-Thought):** the model thinks through the problem step by step before acting, improving accuracy on complex tasks.
- **Planning:** the agent creates an ordered sequence of sub-tasks needed to reach the final goal.
- **Tool/Action Selection:** at each step, the agent decides whether to call a tool (e.g., a search API, database query, or code execution) or respond directly.
- **Observation and Reflection:** after each action, the agent evaluates the result and decides whether to continue, retry, or change its plan (the ReAct — Reason + Act — loop).
- **Memory:** short-term (within a single run) and long-term (stored across sessions) memory allow the agent to maintain context and learn from past interactions.

## 4. Key Algorithms that Drive AI Functionality

- **Large Language Models (LLMs)** such as GPT-based models act as the "reasoning engine" that interprets instructions and generates responses or action plans.
- **Retrieval-Augmented Generation (RAG):** combines a language model with a knowledge base or vector database so the agent can fetch relevant, up-to-date information before answering.
- **Embeddings and Semantic Search:** convert text into numerical vectors so that similar pieces of information can be retrieved quickly and accurately.
- **Function/Tool Calling:** a structured mechanism that lets the model invoke external functions (APIs, code, RSS feeds, databases) with the correct parameters.
- **Workflow Orchestration:** tools such as n8n, LangChain, and similar frameworks coordinate the sequence of triggers, data transformations, AI calls, and outputs that make up an end-to-end agent.

## 5. Industry Applications of Agentic AI

| Industry | Use Case | How Agentic AI Helps |
|---|---|---|
| Media & News | Automated Tech News Research Agent | An n8n-based agent collects articles from multiple RSS feeds (TechCrunch, BBC, The Verge), filters and cleans the data, then uses an LLM to categorise and summarise each article — producing a ready-to-read daily digest without manual effort. |
| Healthcare | Clinical decision support / triage assistants | Agents can analyse patient symptoms, retrieve relevant medical literature via RAG, prioritise cases by urgency, and draft preliminary notes for clinicians — improving response time while keeping a human in the loop for final decisions. |
| Finance | Fraud detection & report generation | Agents continuously monitor transactions, flag anomalies, query relevant databases, and automatically compile compliance or risk reports for human review. |
| Customer Support | AI support triage agents | Incoming tickets are automatically categorised by urgency and topic, routed to the right team, and drafted responses are generated — reducing resolution time. |
| Project Management | AI project manager assistants | Agents track task status, summarise progress across tools, send reminders, and generate status reports automatically. |

## 6. Use Case Spotlight: AI in Healthcare

Healthcare is one of the sectors where agentic AI offers the highest potential impact, but also carries the greatest responsibility.

### Benefits
- **Faster triage:** AI agents can quickly review patient-reported symptoms and prioritise urgent cases for a doctor's attention.
- **Knowledge retrieval:** Using RAG over verified medical guidelines, an agent can surface the most relevant treatment protocols for a given condition.
- **Administrative automation:** scheduling, summarising consultation notes, and generating discharge instructions can all be automated, freeing up clinical staff time.
- **Continuous monitoring:** agents connected to wearable devices can flag abnormal readings and alert care teams proactively.

### Ethical Implications
- **Accountability:** a clear human-in-the-loop must remain responsible for final medical decisions — AI should assist, not replace, clinical judgement.
- **Bias and fairness:** training data must be representative; otherwise the agent may give less accurate recommendations for under-represented patient groups.
- **Privacy:** patient data used by agents (for retrieval or memory) must be handled in compliance with regulations such as HIPAA/GDPR.
- **Transparency:** patients and clinicians should be able to understand why an agent made a particular recommendation (explainability).
- **Over-reliance:** there is a risk that clinicians may over-trust automated suggestions, so systems should be designed to encourage critical review rather than blind acceptance.

## 7. Broader Ethical Considerations in Agentic AI

- **Autonomy vs. control:** as agents are given more freedom to act, robust guardrails and approval steps are needed for high-impact actions.
- **Data security:** agents that connect to external tools and APIs increase the attack surface, so credentials and tokens must be stored securely and never exposed in code or configuration files.
- **Job impact:** automation of research, support, and reporting tasks can change job roles — organisations should plan for re-skilling rather than abrupt displacement.
- **Environmental cost:** running large models at scale has an energy footprint that should be considered when designing always-on agents.
- **Misuse potential:** the same automation capabilities that make agents useful (web access, code execution, messaging) could be misused if not properly access-controlled.

## 8. Trends Shaping the Future of Agentic AI

- Standardised tool-connection protocols (e.g., Model Context Protocol) making it easier for agents to securely connect to many data sources and services.
- Multi-agent collaboration, where specialised agents (research, coding, review) work together on complex tasks.
- Improved memory architectures allowing agents to retain context over long periods and across sessions.
- Stronger evaluation and monitoring frameworks to test agent reliability before deployment in production.
- Greater emphasis on responsible AI governance, including audit trails for autonomous actions.

## 9. Case Study: Tech News Research Agent (Project Built)

As part of this internship, an autonomous Tech News Research Agent was built using **n8n** to demonstrate the practical application of the concepts discussed above:

- A **Schedule Trigger** runs the workflow automatically every day.
- Three **RSS Feed Read** nodes (TechCrunch, BBC Technology, The Verge) collect the latest tech articles in parallel — demonstrating data aggregation from multiple sources.
- A **Merge** node combines all articles, and a **Limit** node restricts processing to the top 10 items for efficiency.
- A **Code** node cleans and trims each article to its title, link, and summary before passing it on — reducing the data sent to the AI model.
- A **Basic LLM Chain** (powered by an OpenAI model) categorises each article (AI, Hardware, Software, Business, Cybersecurity) and writes a concise two-line summary with the source link.

This project mirrors the broader objectives of Agentic AI: it operates autonomously on a schedule, makes decisions about how to categorise content, uses external tools (RSS feeds and an LLM API), and produces a structured, useful output without manual intervention — illustrating how the same principles scale to the healthcare, finance, and support use cases discussed earlier.

## 10. Conclusion

Agentic AI represents a significant shift from passive, single-response AI models towards autonomous systems capable of planning, acting, and adapting to achieve goals. While the potential benefits across industries such as healthcare, finance, customer support, and media are substantial, realising this potential responsibly requires careful attention to decision-making transparency, data security, fairness, and human oversight. As tooling and protocols continue to mature, agentic systems are likely to become a standard part of how organisations automate complex, multi-step work.

## 11. References / Further Reading

- n8n Documentation — Workflow Automation
- Model Context Protocol (MCP) specification
- OpenAI API Documentation — Function/Tool Calling
