# Google_Prompt_to_Action
This project marks the beginning of my journey into AI agent development, exploring how intelligent systems can take actions to achieve tasks autonomously.
1. Project Overview

In this hackathon, I built an Enterprise AI Agent for Automated Incident Triage using the Google AI Agent Development Kit (ADK).
The agent takes incoming system alerts (from a JSON log file) and:
Reads & summarises alerts
Ranks alerts by severity
Identifies critical incidents
Creates suggested mitigation actions
Asks for human approval when required
Generates a final actionable report

This simulates how modern incident-response teams automate triage in real enterprise environments.
This project was implemented entirely in a Kaggle Notebook using the Gemini 2.0 Flash model and the ADK multi-tool agent system

2. Problem Statement
Large enterprise systems generate hundreds of logs and alerts every minute.
Manually reviewing these leads to:
Delayed incident detection
Missed critical alerts
Excessive staff workload
Slow response time
The goal is to create an AI Triage Agent that automatically:
✔ Processes alerts
✔ Organizes them by severity
✔ Recommends mitigation
✔ Requests approval where needed
This reduces human noise and allows faster and more accurate incident handling.

Why agents? -- Why are agents the right solution to this problem
A. Summarizes Alerts
Reads the alert file (sample_alerts.json) and produces a human-readable summary.
B. Ranks Alerts
Sorts incidents based on severity such as:
CRITICAL
HIGH
MEDIUM
LOW
C. Suggests Actions
For high-severity alerts, the agent proposes:
mitigation steps
actions to be taken
creation of incident tickets
D. Approval Workflow
For actions like shutting down a server or restarting a service, the agent:
pauses
asks for human confirmation
continues workflow after approval
E. Final Incident Report
Generates a structured output that can be used by DevOps or IT teams.

What you created -- What's the overall architecture?
User Request → Triage Agent → Tools → Approval Step → Final Output
Flow
Agent loads alert JSON file
Calls summarize_alerts
Calls triage_alerts
If mitigation requires approval → pauses
After approval → continues
Returns final incident triage summary
This mimics a real enterprise triage loop.

**Example Outputs My Agent Generates
**
10 alerts processed. 2 are critical.
Critical alert: High CPU spike on server X.
“Suggested mitigation: Restart service X.
Action requires approval. Proceed?
Mitigation approved. Creating ticket.

** The Build -- How you created it, what tools or technologies you used.
**
Notebook environment: Kaggle
API integration: GOOGLE_API_KEY via Kaggle Secrets
ADK components used:
tool decorator
Tool schema class
AsyncAgentRunner
SessionService
Gemini 2.0 Flash model
A simple dataset (sample_alerts.json) was used for demonstration.

**Why solution is useful?
**Enterprises can use systems like this to:

✔ Reduce incident-response time
✔ Automate repetitive triage tasks
✔ Improve reliability
✔ Lower operational cost
✔ Support DevOps teams with continuous monitoring

This agent is a foundational step that can be extended into:
Auto-ticketing
Service restarts
Infrastructure automation
PagerDuty integrations

Conclusion

This project demonstrates how AI agents can bring automation, intelligence, and speed to enterprise incident-triage workflows. Even with a simple dataset, the agent shows how powerful ADK-based systems can be when handling real-world operational alerts.

During this project I learned:
How multi-tool agents work
How to define custom tools
How to build an approval workflow
How to use ADK with Gemini models
How enterprise triage systems operate
How to run async agents in Kaggle

