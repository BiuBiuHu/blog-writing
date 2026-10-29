# Blog Writing

[中文](README.md)

A Codex skill for turning first-hand project work into readable blog posts. It supports Chinese and English writing, HTML/CSS explanatory diagrams, and verified publication when the user authorizes it.

The emphasis is on what happened, why the author changed direction, and what remains unresolved. It does not force every story into a list of principles, a formulaic introduction, or a polished closing slogan. It makes no promises about search rankings.

## Capabilities

- **Writing and revision:** Verify facts against first-hand material and preserve the author's confirmed motives, terminology, and edits. Use Arabic numerals for numbered sections.
- **Chinese and English:** Complete blog deliveries default to both languages. Rewrite naturally in English while keeping the facts, numbers, sources, and uncertainty aligned. Respect requests for a single language or a small edit.
- **Explanatory figures:** Lay out HTML/CSS, render in a browser, export PNG, and inspect the actual result. Localize diagram text and retain editable sources.
- **Publication checks:** Verify mobile reading, language switching, image loading and zoom where available, metadata, and existing feeds/sitemaps. Preview committed content before an authorized production release.
- **Traceability:** Reconcile source commits, CI artifacts, platform versions, and public URLs, with a rollback baseline and an honest verification record.

This is an instruction package, not a standalone blog application. It relies on the agent's available file, Git, browser, and deployment tools. It does not automatically install tools, buy services, or provision cloud resources. The skill instructions are primarily in Chinese; the workflow produces either language as requested.

## Install in Codex

If a skill with this name is not already installed:

```bash
git clone https://github.com/BiuBiuHu/blog-writing.git "${CODEX_HOME:-$HOME/.codex}/skills/blog-writing"
```

Alternatively, use Codex's `skill-installer` with this repository, its root as the skill path, and `blog-writing` as the installed name. If the directory already exists, back it up and inspect differences before replacing anything.

Invoke `$blog-writing` in the next conversation turn after installation.

## Examples

Draft:

> Use $blog-writing to write about this implementation. Keep the real decisions and avoid generic lessons after every section. Draft in Chinese first; do not publish.

Bilingual preparation:

> The Chinese version is approved. Prepare Chinese and English posts with localized explanatory diagrams rendered from HTML, numbered sections, and local checks. Do not publish yet.

Publication:

> Use $blog-writing to put both posts and their figures into the existing blog, verify them, and publish.

Drafting, saving to a blog, and public publication are separate scopes. Once the user explicitly authorizes verification followed by publication, complete the authorized steps without asking for the same approval again. Installing the skill does not authorize automatic publication of future articles.

## Workflow

1. Identify the project, evidence, and approved draft.
2. Write or revise in the requested languages.
3. Render HTML/CSS figures, export PNG, and inspect them.
4. Check facts, metadata, asset paths, and desktop/mobile reading.
5. For authorized releases, commit the candidate and verify an isolated preview.
6. Release according to the project's existing gates, then verify public URLs and deployed versions.

There is no fixed word count, section count, or figure count. Tutorials and personal implementation accounts can use different structures. Site conventions are discovered from the target project.

## Files

| File | Purpose |
|---|---|
| [SKILL.md](SKILL.md) | Entry point, editorial preferences, scope, and workflow routing |
| [Editorial quality](references/editorial-quality.md) | Reader value, first-hand narrative, detail, and formulaic-writing checks |
| [Bilingual publishing workflow](references/bilingual-publishing-workflow.md) | Figures, local/preview/production checks, and release traceability |
| [Site adaptation](references/site-context.md) | Discovering content, locale, and deployment conventions |
| [Codex metadata](agents/openai.yaml) | Display name and invocation prompt |

## Adapting to your blog

Astro paths such as `src/content/blog/` and filename suffixes such as `-en.md` are examples, not universal requirements. Read the target schema, templates, locale routes, and CI. Keep the project's existing Vercel, Cloudflare, or other hosting setup.

This repository includes no deployment credentials, cloud-account configuration, user data, private posts, or screenshot tooling. Release checks require the relevant tools and permissions. Record checks that could not be performed rather than claiming they passed.

## Practice behind the skill

The workflow was refined through bilingual writing, HTML figures, and publication checks:

- [Chinese account of the Grok Bot / Cloudflare migration](https://www.peak-lake.com/blog/grok-bot-vercel-cloudflare)
- [Why We Moved Anpai Calendar to Cloudflare After Starting to Use Grok Bot](https://www.peak-lake.com/en/blog/grok-bot-vercel-cloudflare)

## License

[MIT](LICENSE).
