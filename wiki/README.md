# Wiki Database Readme

![Wiki Icon](../assets/wiki_icon.png)

This directory contains the persistent, structured markdown knowledge base managed by the **Project Cortex** skill. 

Rather than letting notes and codebase documentation get lost in chat histories, this wiki serves as the centralized "ground truth" for the project.

## How it Works

The wiki is co-maintained by humans and an LLM agent (like Antigravity). The agent follows a strict declarative workflow defined in the system's global config to keep the documentation healthy, integrated, and accurate.

```
wiki/
├── index.md             # The entry point, topic map, and navigation index
├── README.md            # This file (meta documentation)
└── [topic-pages].md     # Interconnected concept/entity files
```

---

## Guide for Humans

### 1. Structure of a Wiki Page
Every page in this directory (except index/meta files) must follow a structured schema:
*   **YAML Frontmatter:** Tracks metadata like title, page type (`concept`, `tool`, `log`, etc.), tags, and creation/update dates.
*   **Summary:** A concise definition of the topic.
*   **Key Facts:** A high-level bulleted list of essential points.
*   **Details:** Deep dive explanations.
*   **Related:** Navigation links to parent topics or related pages.
*   **Sources:** Explicit citation of where the facts came from (with access dates).

### 2. Standard Prompts
You can interact with your AI assistant using these natural language commands to update or audit this folder:

*   **Ingest raw text/links:** 
    > *"Ingest this note: [your text]"*
    > *"Add this documentation to the wiki: [paste text/links]"*
*   **Audit & Clean the folder:**
    > *"Audit the wiki"*
    > *"Lint the wiki"*
    *   *Note: This will check for orphan pages (pages not linked in `index.md`), deduplicate similar topics, and search for conflicting information.*
*   **Create specific pages:**
    > *"Create a new wiki page for [Topic]"*

---

## Guide for the LLM Maintainer

When acting as the maintainer of this directory:
1. **Always search before writing:** Grep or list files to verify if a topic already exists before creating a duplicate.
2. **Track Provenance:** Every fact must be traced back to a source listed in the `## Sources` section at the bottom of the page.
3. **Keep it Linked:** Every new page must be linked in `wiki/index.md` under the appropriate section and should contain a link back to its parent/related topics.
4. **Use Standard Links:** Only use standard relative markdown links (e.g., `[Title](relative/path.md)`). Never use `[[wikilinks]]`.
