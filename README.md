# Auto-Fix Agent: The Self-Healing Repository

>Witness the future of software maintenance. The Auto-Fix Agent is an autonomous AI engineer that doesn't just report bugs it fixes them for you. This demo shows the agent acting as a "digital first responder," instantly transforming a vague user bug report into a ready-to-merge GitHub Pull Request. Watch as it autonomously finds the faulty code, debugs it, and patches it automatically, moving us closer to the reality of a self-healing repository.

**Track:** Enterprise Agents

**Built With:** Google Gemini 1.5 Pro, Google AI SDK, PyGithub

> **"The first AI agent that doesn't just report bugs it fixes them."**

## 1. The Problem: The Maintenance Trap
In modern software engineering, **maintenance consumes 42-50% of developer time**. The workflow for fixing a reported bug is tedious and repetitive:
1.  Receive a vague report (e.g., *"The app crashes on division"*).
2.  Manually search the codebase to find the relevant file.
3.  Read code to understand the context.
4.  Write a patch and submit a Pull Request (PR).

This "context switching" kills productivity. Senior engineers waste hours on "Level 1" bugs instead of building new features.

## 2. The Solution: Autonomous Triage
**Auto-Fix Agent** is an autonomous "Level 1 Support Engineer" that lives in your repository. It acts as a "Digital First Responder."

When a bug is reported, the agent:
* **Reasons:** Analyzes the error message to hypothesize the root cause.
* **Investigates:** Autonomously navigates the file system using GitHub Search tools.
* **Repairs:** Writes the specific code fix (not just a suggestion).
* **Deploys:** Submits a formatted Pull Request for human review.

## 3. Technical Architecture
The system is built on a **Multi-Agent Cognitive Architecture** powered by **Gemini 1.5 Pro** (chosen for its large context window and code-reasoning capabilities).

### The "Brain" (Reasoning Engine)
Unlike standard chatbots, this agent uses a **Chain-of-Thought** process:
1.  **Hypothesis Generation:** *"User reports ZeroDivisionError. I should look for division operations in `calculator.py`."*
2.  **Tool Execution:** It calls defined Python functions to interact with the outside world.
3.  **Self-Correction:** If a search yields no results, it refines its query and retries.

### The "Hands" (Tooling Layer)
The agent is equipped with three custom tools connected to the **GitHub REST API**:
* `search_codebase(query)`: Semantic search to locate relevant files.
* `read_file(path)`: Fetches raw content from the target branch.
* `create_fix_pull_request(diff)`: Automates branching, committing, and PR creation.

### Resilience & Observability
* **Rate Limit Handling:** Implements exponential backoff to handle GitHub API secondary rate limits (403 Forbidden) and Gemini quotas.
* **Traceability:** Every action (search, read, write) is logged, providing full observability into the agent's decision-making process.

## 4. Key Value Proposition

| Feature | Traditional Workflow | Auto-Fix Agent Workflow |
| :--- | :--- | :--- |
| **Discovery** | Manual grep/search (15-30 mins) | **Instant Semantic Search (<10s)** |
| **Fixing** | Context switch & coding (30+ mins) | **Automated Patch Generation** |
| **Process** | Manual Git commands | **One-click PR Generation** |
| **Role** | Distracted Senior Dev | **24/7 Autonomous Support** |

## 5. Future Roadmap
* **CI/CD Integration:** Automatically run unit tests on the agent's PR to verify the fix.
* **RAG Implementation:** Index the entire repository into a Vector Database for instant context retrieval on massive codebases.

---
