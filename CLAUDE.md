Objective:
Ensure access to project and company documentation before performing any domain-specific reasoning.

Instructions:

1. Memory Verification
   - Check project memory for the registered location of the ALuaAzul meta-docs repository.
   - Specifically verify whether the path to the ALuaAzul-meta-docs repository is stored.

2. If Not Found in Memory
   - Do NOT attempt to infer or guess the repository location.
   - Ask the user explicitly:
     "Where is the ALuaAzul-meta-docs repository located?"
   - Wait for the user to provide the exact path.
   - After receiving the path, store this location in project memory for future use.

3. Read Project Docs First
   - Read docs/index.md from the current project directory.
   - This is the primary navigation map for this project — it lists every doc file and when to use each.
   - Do NOT read other files in docs/ unless the task requires it. Use the index to decide.

4. Read Meta-Docs Indexes (company-level context)
   - Read ONLY the index files below. Do NOT read individual files speculatively.

   Required indexes:
     - 01-business/index.md  → what projects exist, their type and description
     - 06-ai/index.md        → what AI docs exist per project and what each covers

5. Navigate on Demand
   - After reading the indexes, open additional files ONLY if the current task requires it.
   - For this project (marlondantas-dev), the AI docs are under:
       06-ai/marlondantas-dev/

6. Behavior Constraints
   - Never assume undocumented behavior.
   - Never derive business rules from code without confirmation from docs/ or meta-docs.
   - If documentation is missing or incomplete, explicitly notify the user before proceeding.
   - This project is in its FIRST STAGE — prioritize simplicity and speed of delivery.
   - Do not suggest complex infrastructure or over-engineered solutions unless explicitly asked.
   - The primary user is the owner — optimize for that, not for scale.
