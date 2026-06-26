# Agentic Skill Installation Guide

Because Antigravity is a fully autonomous coding agent, **you don't have to install this skill manually.** You can simply command Antigravity to install it for you!

Here is the exact prompt you can copy and paste into a fresh Antigravity chat window to make it self-install this skill.

---

## The Copy-Paste Installer Prompt

Copy the text block below, customize the repository path if needed, and send it to a fresh Antigravity session:

```text
Please register the Project Cortex skill natively in my global Antigravity config. 

The source repository is currently located at:
https://github.com/DamirLukina88/LLM-wiki-system-skill wiki system skill

Please perform the following steps:
1. Locate the source 'SKILL.md' file inside the repository path.
2. In my global configuration directory (check '~/.gemini/config/plugins/'), create a new plugin directory named 'llm-wiki-plugin'.
3. Write a standard 'plugin.json' manifest inside that directory specifying name: "llm-wiki-plugin", version: "1.0.0", and a description.
4. Copy the content of the source 'SKILL.md' into 'llm-wiki-plugin/skills/project-cortex/SKILL.md'.
5. Audit and verify that all directories were created correctly.
```

---

## How It Works Behind the Scenes

When you paste this prompt to a new Antigravity instance, the agent will:
1. **Discover its own config path:** It knows where its global `~/.gemini/config/plugins` directory is located.
2. **Access filesystem tools:** It will read the `SKILL.md` from the path you provided.
3. **Write the plugin setup:** It will create the necessary directory structure and write `plugin.json` and the copied `SKILL.md` to the correct target paths.
4. **Register the skill:** On your next prompt, the skill will be natively loaded on the agent's available skills list!
