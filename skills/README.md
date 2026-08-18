# AIRBDS assessment skills

This directory contains skills that can be imported into AI assistants to conduct AIRBDS assessments. They conform to the [agentskills.io](https://agentskills.io) standard.

<!-- The two version numbers below are stamped by the release scripts in
     AIBIO-UK/airbds-dev; the comment markers are how they find them. Keep the
     markers if you reword this sentence, or the next release will fail rather
     than publish a stale version. -->
There is currently one skill at [`skills/airbds-assessment-skill.zip`](https://github.com/AIBIO-UK/airbds-core/raw/main/skills/airbds-assessment-skill.zip), currently at version <!--skill-version-->0.9.0<!--/skill-version--> and assessing against [AIRBDS metric](https://github.com/AIBIO-UK/airbds-core/blob/main/airbds_metric.yaml) v<!--metric-version-->1.0.1<!--/metric-version-->. The zip itself is the skill containing all its components.

## Installation instructions

With many assistants (e.g. Claude Code, Hermes Agent) all you need to do is

1. Download [the skill](https://github.com/AIBIO-UK/airbds-core/raw/main/skills/airbds-assessment-skill.zip).
2. Give the zip to the assistant — attach it to a message, or point the assistant at the downloaded file — and ask it to install the skill.

In some cases, such as for Claude Web, the assistant can't do this directly but will give you the instructions for a manual installation when you ask it to install the skill zip.

Some assistants, such as Gemini, do not support the agentskills.io standard. They may have alternative formats - Gemini, for example, has 'Gems'. We do not publish the skill in those formats.

## Using the skill

Once the skill is installed, ask your assistant something like

> Assess https://example.org/some-dataset against AIRBDS.

We recommend that you use the most capable model you have available to perform an AIRBDS dataset assessment, in order to get the most comprehensive investigation and analysis.

## References

Anthropic's full guide: <https://support.claude.com/en/articles/12512180-use-skills-in-claude>
