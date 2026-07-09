# PATCH_MANIFEST.md

Patch Name : TSA Runtime Mode + AI Contract v1.7  
Version    : 1.7.0  
Scope      : Runtime, Prompt Runtime, AI Contract Governance  

---

# Replace / Update

```text
README.md
README_FIRST.md
README for agent.md
runtime/MODE_SELECTOR.md
runtime/BOOT.md
runtime/EXECUTION.md
runtime/DEBUG_LOOP.md
runtime/KNOWLEDGE_UPDATE.md
runtime/SHUTDOWN.md
prompt/PROMPT_SELECTOR.md
prompt/MODE_0_DIRECT.md
prompt/MODE_1_MICRO_PATCH.md
prompt/MODE_2_FEATURE_PATCH.md
prompt/MODE_3_FOUNDATION.md
prompt/MODE_4_REVIEW.md
kernel/last! AI CONTRACT.md
```

---

# Reason

- Add Runtime Mode so TSA remains lightweight for small tasks.
- Add Mode Selector as runtime classifier.
- Separate human README and agent README.
- Keep Debug Loop detail only in `runtime/DEBUG_LOOP.md`.
- AI Contract updated to v1.7.0 to add documentation governance agreements 47–50.
- Prevent duplicate responsibility in AI Contract and Debug Loop.

---

# Keep / Do Not Change

```text
Sprint 0–9 documents
Existing project documentation
Existing examples unless explicitly moved
```

---

# Status

LOCKED
