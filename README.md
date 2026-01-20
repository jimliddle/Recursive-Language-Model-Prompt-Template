This repo provide a prompt template that simulates an RLM (as per https://arxiv.org/pdf/2512.24601v1) for an LLM.

This prompt:

- Forces structured thinking: The explicit steps prevent the model from just "vibes-based" reasoning over a huge input

- Locality constraint: "Do NOT reference information outside the current subset" is a way to simulate the isolation that real RLMs enforce mechanically

- Hierarchical synthesis: Mirrors how the paper's approach aggregates results bottom-up

- Clear output structure: Makes it easy to see where reasoning might have gone wrong

Limitations:

The model still sees everything - The whole point of RLMs is that the root model never sees the full string directly in its context.
No actual recursion - Real RLMs spawn sub-calls that have genuinely isolated context. This prompt simulates the structure but not the mechanism. The model has to pretend it can't see things it  can see.
Single-pass limitation - True RLMs can iterate dynamically based on what they find. This prompt asks for a plan upfront, which may not adapt well to unexpected document structure.

What its Useful For:

- Large documents

- Long transcripts

- Codebases

- Research synthesis

- Compliance and audit tasks

- Knowledge extraction pipelines
