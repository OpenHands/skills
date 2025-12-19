# OpenHands Skills Registry

Public registry of **Skills** for [OpenHands](https://github.com/OpenHands/OpenHands) - reusable guidelines that customize agent behavior.
Check the [documentation](https://docs.openhands.dev/overview/skills) for more information.

> **Note**: Skills were previously called Microagents. The `.openhands/microagents/` folder path still works for backward compatibility.

## What are Skills?

Skills are Markdown files containing instructions and best practices that guide OpenHands agents. They provide domain expertise (git, docker, kubernetes), encode best practices (code review, security), and eliminate repetitive instructions.

## Skill Types

### General Skills
Always loaded as context. No frontmatter needed.

```markdown
# Repository Guidelines
This project uses React and Node.js. Run `npm install` to set up...
```

### Keyword-Triggered Skills
Loaded only when trigger words appear in user prompts. Requires frontmatter.

```markdown
---
triggers:
  - docker
  - dockerfile
---

# Docker Guidelines
When working with Docker containers...
```

## Contributing

To contribute a skill:

1. Fork this repository
2. Add a `.md` file in the `skills/` directory
3. For keyword-triggered skills, include frontmatter with `triggers` list
4. Submit a pull request

**Good skills are:**
- Specific and actionable
- Focused on a single domain or task
- Include concrete examples
- Use relevant trigger keywords (for keyword-triggered skills)

## Frontmatter Reference

**General Skills**: No frontmatter needed

**Keyword-Triggered Skills**: Frontmatter required to specify triggers
```yaml
---
triggers:
  - keyword1
  - keyword2
agent: CodeActAgent  # Optional, defaults to CodeActAgent
---
```

## Examples

See the [`skills/`](skills/) directory for examples like [`github.md`](skills/github.md), [`docker.md`](skills/docker.md), [`code-review.md`](skills/code-review.md).

## Learn More

- [OpenHands Documentation](https://docs.openhands.dev)
- [OpenHands Repository](https://github.com/OpenHands/OpenHands)
- [Software Agent SDK](https://github.com/OpenHands/software-agent-sdk)
