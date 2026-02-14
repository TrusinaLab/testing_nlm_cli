# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a scientific writing project focused on creating a review article about gastrulation in developmental biology. The primary deliverable is `Intro_gastrulation.md`, a review article targeted at a physics-minded audience that bridges physics and developmental biology.

## Key Documents

- **Intro_gastrulation.md** - Main review article on gastrulation mechanisms, computational modeling, and self-organization principles
- **claude_writing_instructions/master_writing_agent_instructions.md** - Comprehensive writing guidelines synthesized from Strunk & White, Zinsser, Pinker, and King. Consult this for writing principles, style guidance, and revision practices.

## Audience and Register

The target audience is a **physics-minded scientific community**. Writing should:

- **Preserve scientific terminology**: Terms like "morphogenetic patterning", "gastrulation", "mesoderm", "amniotes" are accessible to this audience and should remain. Define on first use when helpful, but don't oversimplify.
- **Use physics language freely**: "continuum mechanics", "reaction-diffusion", "self-organisation", "symmetry breaking" are native to the audience.
- **Balance clarity with precision**: Activate verbs, cut redundancy, fix typos, and smooth transitions—but do NOT flatten the scientific register or strip domain-specific terminology.
- **Only flag truly obscure jargon**: Terms should be flagged only if both obscure AND cannot be inferred from context. This audience is comfortable looking up unfamiliar terms.

## Writing Workflow

When revising or adding to `Intro_gastrulation.md`:

1. **Read ./claude_writing_instructions/master_writing_agent_instructions.md** for comprehensive writing principles
2. **Apply the revision checklist** (Part V in master_writing_agent_instructions.md)
3. **Respect the scientific register** - this is not popular science writing
4. **Maintain IMRAD-style structure** where appropriate for scientific reviews
5. **Use active voice** and strong verbs while preserving necessary technical terminology

## Fact Verification with NotebookLM

**IMPORTANT:** When prompted to verify statements to `Intro_gastrulation.md`, always use the `nlm` CLI to check against the reference notebook first.

**Primary Reference Notebook:**
- **ID:** `8f8a7114-b1e5-4921-b7b8-e1d3d6f514c4`
- **Title:** "Review on models of gastrulation"
- **Sources:** 42 research sources

**Verification Workflow:**

1. **When prompted to veryfy statements**, query the notebook to verify statements:
   ```bash
   nlm query <notebook-id> "your question about gastrulation"
   ```

2. **To get source details** from the notebook:
   ```bash
   nlm list sources --notebook <notebook-id>
   ```

3. **To get specific content** from a source:
   ```bash
   nlm content <source-id>
   ```

**Usage Example:**
- When asked to verify statement: "reaction-diffusion models describe gradient-driven patterning in gastrulation", query the notebook to verify this claim and find supporting sources
- Use notebook responses to inform accurate scientific statements and proper citations

## Project Structure

```
.
├── CLAUDE.md                       # This file - guidance for Claude Code
├── Intro_gastrulation.md           # Main review article
├── README.md                       # Project README (currently empty)
├── claude_writing_instructions/    # Writing guidelines and instructions
│   └── master_writing_agent_instructions.md
├── nlm_accessories/                # Supporting files (e.g., cookies for web access)
└── pyproject.toml                  # Python project metadata (minimal dependencies)
```

## Technical Notes

- Python 3.14+ required (specified in pyproject.toml)
- No code execution or testing needed - this is a documentation/writing project
- Git is used for version control of the writing
