# Day 5: Context Engineering - The 60-Day Claude Challenge

## 1. Prompt A (Without Context)

**Prompt Used:**
Create a 30-day learning roadmap.
Include:
- Weekly milestones
- Daily tasks
- Resources
- Projects
- Final outcome
Make it practical and beginner-friendly.

**Output Received:**
The AI generated a generic "30-Day Learning Roadmap." 
- **Milestones:** Vague concepts like "Master the fundamentals" and "Go deeper."
- **Tasks:** General instructions like "Concepts review" and "Deep dive topics."
- **Resources:** Broad suggestions like "YouTube crash courses" and "Official documentation."
- **Projects:** "Mini-project using core skills."

---

## 2. Prompt B (With Context)

**Prompt Used:**
Create a 30-day learning roadmap.

Context:
- Current Situation: M.Tech professional with ~2 years experience, actively giving AI Engineer interviews.
- Current Skills: LLMs, ML, Python, SQL, AI, RAG, LangChain, LangGraph, FastAPI, Prompt Engineering, Statistics.
- Goal: Secure an AI Engineer job in a month with my desired skill set and good pay.
- Available Time: 4-5 hours per day.
- Experience Level: Intermediate.
- Preferred Learning Style: Videos, Reading material and projects.

Include:
- Weekly milestones
- Daily tasks
- Resources
- Projects
- Final outcome

Make it practical and tailored to my experience level.

**Output Received:**
The AI generated a highly specific "30-Day AI Engineer Roadmap" tailored for 4-5 hrs/day.
- **Milestones:** "Foundation Audit & Interview Positioning", "Advanced AI Systems & MLOps."
- **Tasks:** Specific deep dives like "RAG Architecture Mastery," "LangChain/LangGraph Advanced," and "FastAPI Deployment Patterns."
- **Resources:** Exact industry resources like "Andrej Karpathy YouTube," "Chip Huyen - LLMOps," and "RAGAS + LangSmith."
- **Projects:** "Production RAG Chatbot," "Multi-Agent AI System," and "End-to-End LLM App."

---

## 3. Screenshots

* **Prompt A Output (Generic):** 
 <img width="690" height="1090" alt="30_day_learning_roadmap (1)" src="https://github.com/user-attachments/assets/08ee1d2d-02b9-4a37-8345-9f32733240b9" />


* **Prompt B Output (Personalized):** 
<img width="680" height="1720" alt="ai_engineer_30day_roadmap (1)" src="https://github.com/user-attachments/assets/6296cb77-6ebd-4047-b442-9e31b2acb081" />

---

## 4. Comparison & Observation

**1. Which roadmap feels more personalized?**
Prompt B's roadmap is massively more personalized. Prompt A provided a rigid, empty template that could apply to any subject in the world. Prompt B actively utilized the provided tech stack (Python, LangGraph, RAG) and structured the 30 days exactly around clearing technical AI interviews, complete with MLOps and System Design patterns.

**2. Which roadmap would you actually follow?**
I would absolutely follow the Prompt B roadmap. With a goal of securing an AI Engineer job in a month, I cannot waste time on generic "beginner concepts." Prompt B respects the 4-5 hours/day constraint and pushes directly into building Multi-Agent systems and preparing for system design rounds, which perfectly matches an intermediate M.Tech professional's needs.

**3. What role did context play in improving the result?**
Context acted as the crucial steering wheel. By defining the "Current State" (M.Tech, 2 yrs exp) and "Target State" (AI Engineer job), the LLM stopped guessing. It shifted from generating a boilerplate schedule to acting as a senior tech mentor, providing precise, industry-standard resources (like LangChain Docs, HuggingFace PEFT) and interview strategies.

---

## 5. Key Learnings & Tool Usage

* **Context is King:** The quality of an AI agent's output is directly proportional to the constraints and background data you feed it. Good context reduces hallucination and generic filler.
* **Token Efficiency:** Specifying the experience level as "Intermediate" saved the model from wasting tokens on explaining what Python or Machine Learning is, allowing it to focus on complex architectures.
* **Tool of the Day - Sider AI:** Today I installed and used the **Sider AI** browser extension. It proved incredibly efficient for quickly summarizing the long reading resources (Anthropic and PromptingGuide articles) directly within the active browser tab without needing to switch contexts or copy-paste text into a separate LLM window. It acts as an excellent co-pilot for rapid research.

  **Sider AI in Action:**
<img width="1910" height="868" alt="tool a" src="https://github.com/user-attachments/assets/8cc575e7-38e4-4ba4-b1d4-ab33211fa2d2" />
