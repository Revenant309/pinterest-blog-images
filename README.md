# Pinterest Blog Images

An AI-agent skill for turning a blog post URL or article text into Pinterest image concepts, generated visuals, and accompanying captions.

The workflow covers source review, planning a set of vertical pins, image generation, and delivery of titles, descriptions, hashtags, and calls to action. The skill targets Grok Imagine and the tool interfaces named in its instructions.

## Contents

- [SKILL.md](SKILL.md): skill metadata and workflow.
- [Pinterest guidelines](references/pinterest-guidelines.md): image concepts, prompts, and caption structure.
- [Evaluation examples](evals/evals.json): example inputs and expected behavior.
- [Trigger examples](evals/triggers.json): examples of when the skill should apply.
- [CHANGELOG.md](CHANGELOG.md): release notes.

## Use

Load this directory using your agent environment's skill mechanism. The environment must provide the browsing and image-generation tools referenced in the skill, or equivalent supported integrations.

Example request: "Create Pinterest pins from this blog post URL."

The source files are preserved from the supplied skill archive. Evaluation files describe scenarios and assertions; they are not a standalone test runner.
