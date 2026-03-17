---
name: architect
description: "Multidisciplinary idea and project evaluator. Dispatches 3-6 specialist evaluators in parallel (market, technical, risk, impact, resources, innovation), synthesizes their outputs into a unified assessment with scores, Value Matrix, and actionable next steps. Use when: evaluate idea, assess project, is this worth building, analyze opportunity, score my idea, project evaluation."
license: MIT
metadata:
  version: 1.0.0
  category: evaluation
  tags: [evaluation, multi-agent, scoring, ideas, projects, market-analysis, risk-assessment]
---

# Architect — Multidisciplinary Idea & Project Evaluator

Assess any idea or existing project from multiple angles simultaneously. Dispatches specialist evaluators in parallel, each analyzing from their domain, then synthesizes their outputs into a unified evaluation.

## How It Works

1. **Mode Detection** — auto-detects if input is a new idea or an existing project (by path reference)
2. **Classification** — identifies type: Software / Business / Educational / Social / Creative
3. **Evaluator Selection** — picks 3-6 evaluators based on type:
   - **Risk Assessor**: always included
   - **Technical Architect**: auto-included for software
   - **Market Analyst**: auto-included for revenue-generating ideas
   - **Impact Evaluator**: for social/educational/community ideas
   - **Resource Strategist**: when resource constraints matter
   - **Innovation Scout**: when differentiation or competition are relevant
4. **Parallel Dispatch** — launches evaluators simultaneously using agent files in `agents/`
5. **Synthesis** — `agents/synthesizer.md` resolves conflicts, calculates scores, produces unified output

## Output

- **Opportunity Score** (1-10) with justification
- **Value Matrix**: Commercial / Educational / Social / Technical Feasibility / Risk Level / Resource Efficiency
- **Risk Assessment**: Critical / Significant / Monitoring items + Go/No-Go recommendation
- **Key Synergies**: actions that serve multiple dimensions
- **Prioritized Next Steps**: max 7 focused actions

For existing projects, also includes Project Health Score and Course Corrections.

## Usage

```
"Evaluate my idea: a CLI that generates test suites from codebase analysis"
"Assess the project at ./my-startup — is it worth continuing?"
"Score this concept: marketplace for AI agent skills"
```

## Quick Mode

Use `commands/architect-quick.md` for faster evaluation with only 3 evaluators and no synthesizer agent.

## Structure

```
architect/
├── SKILL.md                          # This file
├── commands/
│   ├── architect.md                  # Main orchestrator
│   ├── architect-quick.md            # Quick mode (3 evaluators)
│   ├── architect-market.md           # Market Analyst standalone
│   ├── architect-technical.md        # Technical Architect standalone
│   ├── architect-risk.md             # Risk Assessor standalone
│   ├── architect-impact.md           # Impact Evaluator standalone
│   ├── architect-resources.md        # Resource Strategist standalone
│   └── architect-innovation.md       # Innovation Scout standalone
├── agents/
│   ├── evaluator-market.md
│   ├── evaluator-technical.md
│   ├── evaluator-risk.md
│   ├── evaluator-impact.md
│   ├── evaluator-resources.md
│   ├── evaluator-innovation.md
│   └── synthesizer.md
├── references/
│   ├── frameworks.md                 # Analysis frameworks (PESTLE, Porter's, etc.)
│   └── scoring-rubrics.md            # 1-10 scoring criteria for all dimensions
└── data/
    ├── context.md                    # Your preferences and skills (fill this in)
    ├── tracking/                     # Evaluator tracking data (auto-populated)
    └── journal/                      # Session logs (auto-populated)
```

## Setup

After installing, fill in `data/context.md` with your:
- Primary interests and domains
- Technical skills and resources
- Risk tolerance
- Evaluation dimension priorities

This personalizes all evaluations to your context.

## Bilingual

All evaluators respond in the same language you write in. Spanish or English — detected automatically.
