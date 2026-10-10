# Memory Sanity Check has moved

Memory Sanity Check is now maintained as part of [Engineering Guardrails](https://github.com/xu-0306/engineering-guardrails).

**Use the maintained skill at [engineering-guardrails/memory-sanity-check](https://github.com/xu-0306/engineering-guardrails/tree/main/memory-sanity-check).** This standalone repository is retained for historical reference and is no longer maintained. Future fixes and issues belong in [Engineering Guardrails](https://github.com/xu-0306/engineering-guardrails/issues).

The migration was merged in [Engineering Guardrails PR #3](https://github.com/xu-0306/engineering-guardrails/pull/3). The maintained version fixes the YAML frontmatter, preserves agreed requirements and authorization, and keeps context checks proportional to the task.

## Update an existing installation

Copy the contents of the maintained `memory-sanity-check/` folder, including `SKILL.md` and `agents/openai.yaml`, into your existing skill directory, for example:

```text
~/.codex/skills/memory-sanity-check/
~/.claude/skills/memory-sanity-check/
```

Preserve any intentional local customizations before replacing files, and keep one installed copy per agent's skill search path. The skill name remains `memory-sanity-check`.

If your installation is a Git clone of this standalone repository, pulling from its old remote will not retrieve future skill updates. Obtain updates from the skill subfolder in Engineering Guardrails; simply changing the remote URL is insufficient because that repository has a different directory layout.

See the [Engineering Guardrails README](https://github.com/xu-0306/engineering-guardrails#installation) for installation and usage details.
