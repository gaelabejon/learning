# Advanced Prompt Engineering Techniques

Curated notes, definitions, and short examples for advanced prompting techniques used to get more reliable, accurate, and controllable outputs from modern large language models (LLMs).

## Contents

- Reference Prompting
- Zero-shot Prompting
- Few-shot Prompting
- Chain-of-Thought (CoT) Prompting
- Generated Knowledge Prompting
- Tree-of-Thought (ToT) Prompting
- Directional Stimulus Prompting
- Chain-of-Density (CoD) Prompting

Each section below includes a short description, when to use the technique, and a compact example you can adapt.

---

## Reference Prompting
Description: Provide explicit reference material (documents, tables, code, or facts) the model should use when composing its answer.

When to use: Tasks requiring factual accuracy, retrieval over a known corpus, or domain-specific constraints.

Example:

"""
Context: [PASTE REFERENCE DOC OR SNIPPET HERE]
Prompt: Using only the information in the Context section, summarize the key security recommendations in 3 bullet points.
"""

---

## Zero-shot Prompting
Description: Ask the model to perform a task without giving any examples.

When to use: Simple or clearly-specified tasks where examples are unnecessary or could bias the response.

Example:

"""
Write a clear, professional email apologizing for a delayed delivery and offering a next-step solution.
"""

---

## Few-shot Prompting
Description: Provide a small number of examples (1–8) to demonstrate the desired format or reasoning pattern.

When to use: Tasks where the output format matters (e.g., JSON, bullet lists) or where model behavior benefits from pattern imitation.

Example:

"""
Example 1:
Q: Convert to a one-line subject. A: "Meeting notes — 2025-10-01"
Example 2:
Q: Convert to a one-line subject. A: "Follow-up: Invoice #12345"

Now convert: Q: Convert to a one-line subject. A:
"""

---

## Chain-of-Thought (CoT) Prompting
Description: Encourage the model to show step-by-step reasoning or intermediate steps before giving the final answer.

When to use: Complex reasoning, math, multi-step decision making, or when you want the model's internal reasoning surfaced for inspection.

Example:

"""
Explain your reasoning step-by-step, then give the final answer.
Question: If a store discounts an item by 20% and then applies a 10% tax on the discounted price, what is the final multiplier applied to the original price?
"""

---

## Generated Knowledge Prompting
Description: First ask the model to generate relevant knowledge/facts, then use that synthesized knowledge as structured input to solve a downstream task.

When to use: When the model can produce useful intermediate knowledge that improves final task performance (e.g., extracting facts, writing constraints, or creating an outline).

Example:

"""
Step 1: List the top 5 legal considerations for publishing a medical app in the EU.
Step 2: Based on the list from Step 1, write a short compliance checklist.
"""

---

## Tree-of-Thought (ToT) Prompting
Description: Explore multiple reasoning paths in a branching/tree structure, evaluate branches, then select or aggregate the best path(s).

When to use: Creative problem solving, planning tasks, or when enumerating alternative solutions is beneficial.

Example (conceptual):

"""
Generate 3 possible approaches to reduce server costs. For each approach, list pros/cons and estimated impact. Finally, recommend one and explain why.
"""

---

## Directional Stimulus Prompting
Description: Provide directional cues or constraints that steer the model’s style, tone, or focus (e.g., "be concise", "use formal tone", "assume the user is a beginner").

When to use: When output style or audience matters.

Example:

"""
Explain OAuth2 in simple terms for a non-technical product manager. Keep it under 150 words and use an analogy.
"""

---

## Chain-of-Density (CoD) Prompting
Description: Provide dense, highly-informative context and structure prompts so the model synthesizes a tightly reasoned chain of facts or arguments.

When to use: Complex synthesis tasks that benefit from compact, information-rich prompts (e.g., legal reasoning, evidence-based summaries).

Example:

"""
Given the following facts [FACT A; FACT B; FACT C], produce a concise argument linking them to support conclusion X. Use explicit citations to facts.
"""

---

## How to use these notes
- Copy any example into your prompt window and replace placeholder context with your real data.
- Prefer explicit instructions for format and length when you need structured outputs.
- Combine techniques: e.g., use Reference Prompting + Few-shot + CoT for complex, factual tasks.

## Contributing
- Open a PR with additions or improved examples.
- Add short, focused examples and include expected outputs when possible.

## Resources & further reading
- Papers and blog posts on Chain-of-Thought, Tree-of-Thought, and prompting best practices.
- Keep external references in a `references.md` file if you add many links.

## License
This folder's notes are provided for study and personal use. If you want a formal license, add a `LICENSE` file to the repository.

---

If you'd like, I can add short runnable examples (curl/OpenAI request templates) or create a `references.md` with links and papers. Tell me what you prefer.