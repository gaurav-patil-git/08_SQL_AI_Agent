# 🤖 SQL AI Agent | Consumer Goods

### Engineer user interface equipped SQL AI Agent with MySQL Workbench integration to generate complex queries. This agent will empower Business/Data Analysts to answer important business questions and facilitate decision making.


## 📌 Table of Contents
- <a href="#overview">Overview</a>
- <a href="#tools-technologies">Tools & Technologies</a>
- <a href="#engineering-agents">Engineering SQL AI Agent</a>
- <a href="#business-questions--key-findings">Business Questions & Key Findings</a>
- <a href="#author-contact">Author & Contact</a>

---
<h2><a class="anchor" id="overview"></a>Overview</h2>

This project aims to design and develop user interface equipped SQL AI Agents with an integration of MySQL Workbench to generate complex SQL statements. This user-friendly and time efficient program will help Business/Data Analysts to answer ad-hoc requests and facilitate decision making.
- Design the entire workflow and Use CrewAI to develop SQL Agent
- Integrate the agent with MySQL workbench
- Develop a low design user interface (UI) using Tkinter 


<h2><a class="anchor" id="tools-technologies"></a>🛠️ Tools & Technologies</h2>

| Tool/Platform | Purpose |
| :--- | :--- |
| Google AI Studio | API Key |
| CrewAI | Develop AI Agents |
| Tkinkter | User Interface |
| ChatGPT & Copilot | Code Assistance |
| Power BI | Visualization |
| Gamma AI | Presentation |


<h2><a class="anchor" id="engineering-agents"></a>🤖 Engineering AI Agents</h2>

## Defining Workflow

![workflow](https://github.com/gaurav-patil-git/08_SQL_AI_Agent/blob/main/visuals/workflow.png)
  
## Developing Agents

### Step 1: Generate API Key

![generate-api-key](https://github.com/gaurav-patil-git/08_SQL_AI_Agent/blob/main/visuals/generate-api-key.png)
  
### Step 2: Prepare and Test LLM
```
from crewai import LLM
llm = LLM(
    model= "gemini/gemini-2.0-flash",
    temperature= 0.1,
    api_key= GEMINI_API_KEY
)
llm.call("What is the full name of APJ Abdul Kalam")
```

### Step 3: Engineer SQL AI Agent
```
agent = Agent(
    llm= llm,
    role="MySQL Query Generator",
    goal= "Generate MySQL queries based on user input.",
    backstory= "You are an SQL expert who writes efficient MySQL queries based on user requirements."
)

task = Task(
    description= f"""Generate an MySQL query based on the following user input:
    '''{user_input}'''
    """,
    agent= agent,
    expected_output= "A valid MySQL query that completes the task described in the user input"
)

crew = Crew(
    agents= [agent],
    tasks= [task]
)
result = str(crew.kickoff().raw).replace("```sql", "").replace("```", "").strip()
result
```

### Step 4: Connecting SQL Agent with MySQL Workbench

- Used **Prompt 1** to generate code and connect MySQL Workbench 


### Step 5: Developing Interface
- Used **Prompt 2** to integrate agent and develop a Tkinter GUI.

![gui-interface](https://github.com/gaurav-patil-git/08_SQL_AI_Agent/blob/main/visuals/gui-interface.png)

<h2><a class="anchor" id="business-questions--key-findings"></a>📈 Business Questions & Key Findings</h2>

### Define business question:

- Business question: Leadership wants to know the total number of newly launched products accross segments and their contribution in revenue.
- Input prompt: 
```
Generate a query to compute the increae in unique product counts in each segments in F.Y. 2021 and
how much revenue the new products contributed in whole of each segment.
Output:
segment | unique_products_2020 | unique_products_2021 | new_unique_products | total_revenue_2021 | revenue_by_new_products | pct_of_total_revenue | rest_revenue
```


### Designing presentation using Gamma AI

- Used **Prompt 3** to design presentation slide

![gamma-draft-ppt](https://github.com/gaurav-patil-git/08_SQL_AI_Agent/blob/main/visuals/gamma-draft-ppt.png)

- Modified and Changed the final formatting with company standard

![presentation-slide](https://github.com/gaurav-patil-git/08_SQL_AI_Agent/blob/main/visuals/presentation-slide.png)

<h2><a class="anchor" id="author-contact"></a>📝 Author & Contact</h2>

**Gaurav Patil** (Data Analyst) 
- 🔗 [LinkedIn](https://www.linkedin.com/in/gaurav-patil-in/)

