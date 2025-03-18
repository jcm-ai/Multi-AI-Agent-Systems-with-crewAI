# 🧍🏻‍♂️🕴🏻🕵🏻 [Multi AI Agent Systems with crewAI](https://www.deeplearning.ai/short-courses/multi-ai-agent-systems-with-crewai/) 🦸🏻‍♂️


This project aims to automate business workflows by utilizing multi-agent AI systems. By harnessing the capabilities of autonomous AI agents, this framework ensures efficient and effective execution of complex, multi-step tasks.

*Goal:*

Designing effective AI agents and organizing a team of these agents to perform intricate, multi-step tasks seamlessly. Our focus is on creating a collaborative ecosystem where AI agents can communicate and cooperate to achieve common objectives.

**Why AI Agents are Superior to LLMs**

*LLMs:*

- Provide human feedback iteratively to refine responses.

- Primarily function as standalone models requiring external input.

*AI Agents:*

- When LLMs operate autonomously, they transform into AI agents.

- AI agents independently ask and answer questions.

- Capable of continuous learning and adaptation based on task requirements and environmental changes.

*Advantages of Multi-Agent Systems:*

1. Scalability: Easily scale tasks by adding more AI agents.

2. Redundancy: Multiple agents can cover for each other, ensuring task completion.

3. Specialization: Different agents can specialize in various aspects of a task, enhancing overall performance.

4. Collaboration: AI agents can work together, sharing knowledge and strategies to tackle complex problems.

*LLMs + Cognitive Capabilities = Intelligent AI Agents*

![331913947](https://github.com/user-attachments/assets/8b514572-ced8-451f-a9cf-decee6bde4c4)

Source: Deeplearning.AI

By integrating cognitive abilities into LLMs, we create AI agents that can think, learn, and act autonomously, leading to more efficient and intelligent business workflows.

### Goal:
Creating capable AI agents and organizing them into collaborative teams to undertake challenging, step-by-step operations.

### Why AI Agents better than LLMs?

* LLMs provide human feedback iteratively to refine responses.

* LLMs primarily function as standalone models requiring external input.

* AI agents when LLMs operate autonomously, they transform into AI agents.

* AI agents independently ask and answer questions.

* AI agents capable of continuous learning and adaptation based on task requirements and environmental changes.

### crewAI Framework

* Crew: The top-level organization that manages AI agent teams, oversees workflows, ensures collaboration, and delivers outcomes.

* CrewAI: A framework that empowers AI agents to be autonomous, adaptive, and collaborative.

### Why Multi AI Agents rather single agents?

* Multiple AI agents can cover for each other, ensuring task completion.

* Different AI agents can specialize in various aspects of a task, enhancing overall performance.

* AI agents can work together, sharing knowledge and strategies to tackle complex problems.

![2](https://github.com/user-attachments/assets/6bb6d2d5-5a84-415f-8909-9092c7243489)

Source: Deeplearning.AI

### Applications of multi-agent systems.
- Tailor resumes and interview prep for job applications
- Research, write and edit technical articles
- Automate customer support inquiries
- Conduct customer outreach campaigns
- Plan and execute events
- Perform financial analysis

### What is Agentic Automation?
New way to write software. Provide fizzy inputs, apply fuzzy tranformations and get fuzzy outputs.

Reason why people love chatGPT: Probablistic nature of the model.

![3](https://github.com/user-attachments/assets/df71442a-2c2c-41a7-885d-2d2c9399e535)

Source: Deeplearning.AI

### How Agentic Automation improves regular automation?
- It is a more human-like interaction, as it is based on natural language.

**Regular Automation (Regular Data Collection and Analysis)**
- Capture information about the company
- Use classification to generate scores for company
- Prioritise for sales

![4](https://github.com/user-attachments/assets/2fc648da-53e5-4b4e-a62d-3018f7ad5c97)

Source: Deeplearning.AI

### Agentic Automation (Data Collection and Analysis using crew)
- AI agent research about company (via Google, internal database)
- AI agent compares companies (new ones, old ones)
- AI agent scores companies (based on parameters)
- AI agent provides intelligent questions to ask based on scores
- AI agent provides results to sales team

![5](https://github.com/user-attachments/assets/dd9532ca-88d7-421f-8233-bc494263a459)


Source: Deeplearning.AI

### Key Components of AI Agent
- **Role:** Assign specialized role to agents
- **Memory:** Provide agents with short-term, long-term and entity memory
- **Tools:** Assign pre-built and custom tools to each agent (eg. for web search)
- **Focus:** Break down task, goals and tools and assign multiple AI agents for better performance
- **Guardrails:** Effectively handle errors, hallucinations and infinite loops.
- **Cooperation:** Perform tasks in series, in parallel and hierarchical fashion



### Role Playing:
More specific role = Better response. Gives clear idea about agent's function in the crew.

**Example:** You are a financial analyst v/s you are FINRA approved financial analyst.

```Bash
from crewai import Agent

agent = Agent(
  role='Data Analyst',
  goal='Extract actionable insights',
  backstory="""You're a data analyst at a large company.
  You're responsible for analyzing data and providing insights
  to the business."""
)
```