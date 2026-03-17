# Architect

Evaluate any idea or project from 6 angles simultaneously. Dispatches specialist evaluators in parallel — market, technical, risk, impact, resources, innovation — then synthesizes their outputs into a unified assessment with scores and actionable next steps.

## Install

```
/plugin marketplace add JuanMarchetto/agent-skills
/plugin install architect@agent-skills
```

Or via [skills.sh](https://skills.sh):
```bash
npx skills add JuanMarchetto/architect-skill
```

Or manually:
```bash
git clone https://github.com/JuanMarchetto/architect-skill.git
cp -r architect-skill ~/.claude/skills/architect
```

## How It Works

```
"Evaluate my idea: a marketplace for AI agent skills"
                        |
            Mode Detection (new idea vs existing project)
                        |
            Select 3-6 Evaluators by type
                        |
    ┌───────┬───────┬───────┬───────┬───────┬───────┐
    │Market │ Tech  │ Risk  │Impact │Resource│Innov. │
    │Analyst│Archit.│Assess.│ Eval. │Strateg.│ Scout │
    └───┬───┴───┬───┴───┬───┴───┬───┴───┬───┴───┬───┘
        └───────┴───────┼───────┴───────┴───────┘
                        |
                   Synthesizer
                        |
            Value Matrix + Opportunity Score
            Risk Assessment + Next Steps
```

Each evaluator runs as a parallel agent with its own analysis frameworks, scoring rubrics, and tracking data. The synthesizer resolves conflicts between evaluators and identifies cross-domain synergies.

## What You Get

- **Opportunity Score** (1-10) with breakdown
- **Value Matrix**: Commercial / Educational / Social / Technical Feasibility / Risk / Resources
- **Risk Assessment**: Go / No-Go / Conditional Go recommendation
- **Prioritized Next Steps**: max 7 actions
- **Project Health Score** (for existing projects)

## Setup

After installing, fill in `data/context.md` with your interests, skills, and risk tolerance to personalize evaluations.

## Real Example — Skills Portfolio Evaluation

Evaluated a portfolio of 25 AI coding assistant skills for open-source potential:

```
OPPORTUNITY SCORE: 7.0/10

VALUE MATRIX
┌──────────────────────┬───────┬─────────────────────────────────────────────┐
│ Dimension            │ Score │ Assessment                                  │
├──────────────────────┼───────┼─────────────────────────────────────────────┤
│ Commercial           │  5/10 │ No direct monetization for markdown skills  │
│ Educational          │  8/10 │ Multi-agent orchestration is novel pattern  │
│ Social               │  6/10 │ Open source contribution, community value   │
│ Technical Feasibility│  9/10 │ All skills working, cross-platform          │
│ Risk Level           │  3/10 │ Low risk — MIT license, no infra costs      │
│ Resource Efficiency  │  8/10 │ Solo developer, zero operational overhead   │
└──────────────────────┴───────┴─────────────────────────────────────────────┘

RISK ASSESSMENT: CONDITIONAL GO
  Critical: No viable direct revenue model
  Significant: Competitive pressure from Anthropic's own tools
  Monitoring: Skills ecosystem adoption rate

NEXT STEPS (prioritized):
  1. Publish top 6 multi-agent skills immediately
  2. Use portfolio as consulting proof-of-work
  3. Apply to Anthropic Ambassador program
  4. Consolidate overlapping skills (mobile cluster, noricum)
  5. Add visual demos to READMEs
```

## Requirements

- Agent tool (for parallel evaluator dispatch)
- WebSearch (evaluators research real market data)

## License

[MIT](LICENSE)
