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

![1](https://github.com/user-attachments/assets/9e6ae792-b7f8-4dcb-a9fc-50d9db7e9e95)
![2](https://github.com/user-attachments/assets/368c954d-5e34-4a0c-b682-c673cf1daaf9)
![3](https://github.com/user-attachments/assets/3e986f69-c7b4-480f-b0af-f199601677cc)

Source: Deeplearning.AI

### Role Playing:
More specific role = Better response. Gives clear idea about agent's function in the crew.

**Example:** You are a financial analyst v/s you are FINRA approved financial analyst.

```Python
from crewai import Agent

agent = Agent(
  role='Data Analyst',
  goal='Extract actionable insights',
  backstory="""You're a data analyst at a large company.
  You're responsible for analyzing data and providing insights
  to the business."""
)
```

### Focus:
Assinging too many tasks, tools, context to a single agent, cause losing essential information and hallucinate.

Therefore, break down task, goals and tools and assign to multiple AI agents for better performance.

```Python
research_ai_task = Task(
    description='Find and summarize the latest AI news',
    expected_output='A bullet list summary of the top 5 most important AI news',
    agent=research_agent,
    tools=[search_tool]
)

research_ops_task = Task(
    description='Find and summarize the latest AI Ops news',
    expected_output='A bullet list summary of the top 5 most important AI Ops news',
    agent=research_agent,
    tools=[search_tool]
)

write_blog_task = Task(
    description="Write a full blog post about the importance of AI and its latest news",
    expected_output='Full blog post that is 4 paragraphs long',
    agent=writer_agent,
    context=[research_ai_task, research_ops_task]
)
```

### Tools:
Assign tools to AI Agents and Tasks for improving execution and performance.

```Python
from crewai import Agent

researcher = Agent(
    role='Market Research Analyst',
    goal='Provide up-to-date market analysis of the AI industry',
    backstory='An expert analyst with a keen eye for market trends.',
    tools=[search_tool, web_rag_tool]
)
```

**Note:** Tasks specific tools override an agent's default tools.

```Python
task = Task(
  description='Find and summarize the latest AI news',
  expected_output='A bullet list summary of the top 5 most important AI news',
  agent=research_agent,
  tools=[search_tool]
)
```
### Collaboration:
AI agents can work together, sharing knowledge and strategies to tackle complex problems.

**Sequential Collaboration**
Ideal for projects requiring tasks to be completed in a specific order.

```Python
report_crew = Crew(
  agents=[researcher, analyst, writer],
  tasks=[research_task, analysis_task, writing_task], # tasks executed in the order of listing, with output of one task serving as context for the next
  process=Process.sequential
)
```
### Hierarchical Collaboration:
- CrewAI automatically creates a manager agent, requiring the specification of a manager language model (manager_llm) for the manager agent.
- THe manager allocates tasks among crew members based on their roles, tools and capabilities.
- The manager evaluates outcomes to ensure they meet the required standards.
- Set process attribute to Process.hierarchical for Crew object
- set `manager_llm` for Crew Object. Mandatory for hierarchical process

```Python
from crewai import Crew
from crewai.process import Process
from langchain_openai import ChatOpenAI

# Example: Creating a crew with a hierarchical process
# Ensure to provide a manager_llm
crew = Crew(
    agents=my_agents,
    tasks=my_tasks,
    process=Process.hierarchical,
    manager_llm=ChatOpenAI(model="gpt-4")
)
```

### Parallel Collaboration:
- Tasks can now be executed asynchronously, allowing for parallel processing and efficiency improvements

```Python
list_ideas = Task(
    description="List of 5 interesting ideas to explore for an article about AI.",
    expected_output="Bullet point list of 5 ideas for an article.",
    agent=researcher,
    async_execution=True # Will be executed asynchronously
)

list_important_history = Task(
    description="Research the history of AI and give me the 5 most important events.",
    expected_output="Bullet point list of 5 important events.",
    agent=researcher,
    async_execution=True # Will be executed asynchronously
)

write_article = Task(
    description="Write an article about AI, its history, and interesting ideas.",
    expected_output="A 4 paragraph article about AI.",
    agent=writer,
    context=[list_ideas, list_important_history] # Will wait for the output of the two tasks to be completed
)
```

### Guardrails:
Implemented at Framework level to prevrnt hallucinations, errors and infintite loops.

### Memory:
CrewAI provides short-term memory, long-term memory, entity memory, and newly identified contextual memory to help AI agents to remember, reason, and learn from past interactions.

**Advantages of Memory:**
- `More contexual awareness`, leading to more coherent and relevant responses
- `Experience Accumulation`, learning from past actions to improve future decision-making and problem-solving.
- `Entity Understanding`, agents can recognize and remember key entities, enhancing understanding.

![1](https://github.com/user-attachments/assets/10cbe0a7-b5c6-433d-88dd-e2bcdf368cc9)

Source: deeplearning.ai


Enable memory by setting memory=True in the Crew objects arguments.

```Python
from crewai import Crew, Agent, Task, Process

# Assemble your crew with memory capabilities
my_crew = Crew(
    agents=[...],
    tasks=[...],
    process=Process.sequential,
    memory=True,
    verbose=True
)
```

![1](https://github.com/user-attachments/assets/90bde76f-c8e7-4f28-ba1b-67fed2844b0c)

Source: deeplearning.ai


