---
hidden: true
---

# Juris Studies authoring style guide

Version 1 — initial draft, November 10, 2026.

This guide records the owner's conventions for Juris Studies, published from the
`ProfMacKelly/juris-studies` repository through Git Sync. Read it alongside
[the repository workflow](../AGENTS.md) and the official GitBook skills. The skills
describe supported GitBook syntax; this guide describes how that syntax is used here.
Explicit instructions for the current task take precedence.

This is an authoring reference. Do not add it to `SUMMARY.md` unless requested.
Its `hidden: true` setting is a navigation convention, not an access restriction.

## Scope and preservation

- Use these templates for new content and requested formatting work. Existing pages
  may use older variants; do not normalize the whole site or unrelated blocks.
- Preserve substantive legal wording, quotations, citations, footnotes, attribution
  statements, licenses, assets, reusable-content references, and intentionally hidden
  content unless the task calls for a change.
- Formatting work does not authorize rewriting legal explanations or independently
  changing licensing claims. Identify questions separately.
- Write actual GitBook source, without the extra backslashes sometimes introduced
  when templates are pasted into chat. Preserve meaningful escapes in existing prose.
- The `***` lines in the owner's supplied template examples only separated examples.
  Do not insert horizontal rules automatically between callouts or annotations.
  Preserve existing page separators unless their removal is requested.

## Callouts

Use `{% hint %}` blocks with the following mappings. The colors are the owner's
editorial categories; do not select a different color based on the ordinary meaning
of “danger,” “success,” or “info.”

| Purpose | Hint style | Heading for new content |
| --- | --- | --- |
| Learning objectives | `info` | `**LEARNING OBJECTIVES 🎯**` |
| Warning | `warning` | A descriptive bold heading appropriate to the warning |
| Law in Practice | `danger` | `**Law in Practice**` |
| Sidebar | `success` | `**Sidebar**` |

### Learning objectives

```markdown
{% hint style="info" %}
**LEARNING OBJECTIVES 🎯**

1. Objective 1.
2. Objective 2.
{% endhint %}
```

Use a numbered list of objectives relevant to the actual lesson. Do not copy generic
objectives from another lesson merely to fill the template.

### Warning

```markdown
{% hint style="warning" %}
**[Descriptive warning heading]**

Warning content.
{% endhint %}
```

The owner has not specified a fixed warning heading. The bracketed heading above
is a placeholder to replace, not literal page content. The underscores in the
original example were a placeholder, not an approved heading.

### Law in Practice

```markdown
{% hint style="danger" %}
**Law in Practice**

Law in Practice content.
{% endhint %}
```

### Sidebar

```markdown
{% hint style="success" %}
**Sidebar**

Sidebar content.
{% endhint %}
```

Use paragraphs or lists according to the sidebar's content. A numbered list is not
required. Keep a blank line between each bold heading and its body; close every hint
with `{% endhint %}`. Do not add a separator after each block.

## Annotations in Git-synced Markdown

For an interactive GitBook annotation, use the owner's linked-text pattern:

```markdown
An explanation containing [annotated text](#user-content-fn-1)[^1].

[^1]: Annotation content.
```

Treat the linked phrase, anchor target, immediately following footnote reference,
and definition as one unit. A plain `[^1]` reference alone is not the prescribed
replacement for this interactive annotation pattern.

- For each distinct annotation on a page, choose an unused identifier and use it
  consistently: `#user-content-fn-2`, `[^2]`, and `[^2]:` belong together.
- Identifiers are local to a page; they do not need to be unique across the site.
- Preserve existing identifiers and intentional repeated references during unrelated
  edits. Do not renumber all annotations just to add one.
- Put definitions at the bottom of the Markdown file. Indent continuation paragraphs
  in a multi-paragraph definition so they remain part of the same note.
- Keep citations and formatting within annotations. Do not confuse an opinion's
  original footnote markers with editorial annotations or convert one into the other.
- Definitions use a closing square bracket and colon: `[^1]:`, not `[^1}:`.
- Do not escape the link parentheses or the annotation brackets in actual source.

### Verification status

The owner reports that this pattern produces hover/click annotations in GitBook.
The same source pattern exists in
[Your Obligation to Know the Law](../sourcebooks/cj-liability/your-obligation-to-know-the-law.md).
This first guide has been checked against repository source; interactive behavior
has not been independently tested while preparing it.

When editing annotations, check both source integrity and the rendered GitBook
preview: activate the annotated phrase and confirm that the intended note appears.
GitHub's Markdown rendering alone does not verify GitBook behavior. Report when
preview or live-site verification is unavailable.

## Attributions and licensing

Use [attributions.md](../attributions.md) as the existing template catalog. Consult
the applicable source-specific example instead of inventing attribution language.
That file contains examples and reusable-content references, not values that can
all be copied unchanged into a new page.

### Select the appropriate template

| Material | Starting point in the catalog | Instructions |
| --- | --- | --- |
| Adapted textbook or other source material | General Attributions & Licensing | Select the relevant source-specific paragraph; retain the source's stated license and identify the material actually used. |
| Adapted case material with editorial notes | Case Attributions | Use the “Editorial Notes, Attributions, and Licensing” structure; preserve applicable editing and elision disclosures. |
| Owner-edited cases and public-domain material | Cases (My Edits) & Public Domain | Preserve the existing reusable-content reference when this is the requested, applicable category. |
| Public-domain material | Public Domain | Use the designated reusable content when applicable; do not infer public-domain status from an absent notice. |
| Original material by the owner | Mine | Use the designated reusable content when applicable; do not apply it to a page containing adapted material without addressing those sources. |
| A definition adapted from Wex | Wex example under General Attributions & Licensing | Replace the term and source information with the actual material used; preserve the applicable attribution and license. |

This table selects editorial templates; it does not independently establish the
copyright or license status of a source. For mixed-source pages, include the
applicable attributions for each source. Flag missing or conflicting information.

### Preserve the attribution structure

The general expandable section uses this wrapper:

```markdown
<details>

<summary>Attributions and Licensing</summary>

[Insert the applicable completed attribution paragraph(s) from attributions.md.]

</details>
```

The case-attribution section instead uses:

```markdown
<summary>Editorial Notes, Attributions, and Licensing</summary>
```

The insertion instruction is a placeholder, not publication text. Do not replace an
existing “Licensing” heading or another intentional variant merely for consistency.

For a new attribution, supply the actual chapter/page title and link, work title and
link, author information, year where applicable, and stated license name and link.
Preserve applicable modification statements. Do not guess missing facts or select
a license solely because another paragraph uses it.

Preserve inline badge markup, including `data-size="line"`. When copying a badge
from a root-level template to a nested page, adjust its relative asset path and
verify the target exists. Do not assume `.gitbook/assets/...` resolves from every
directory. Do not replace remote assets during an unrelated edit.

Preserve existing `{% include "..." %}` reusable-content references. Do not invent
replacement IDs, silently inline their contents, or rewrite the shared content
without a task that calls for it. Confirm accessibility when adding such a reference
to a new page; flag uncertainty rather than substituting guessed wording.

### Catalog details requiring care

The current catalog contains an `app://obsidian.md/...` source link and a
`[Page Name](https://www.example.com/)` placeholder. Do not copy these into new
reader-facing attributions unchanged. Resolve the actual source URL and title or
flag them for the owner. Their presence does not authorize a general cleanup of
the catalog or existing pages.

## Review checklist for content edits

1. Read `AGENTS.md`, this guide, relevant `SUMMARY.md` entries, and the source page.
2. Select only the templates needed for the requested work.
3. Check callout styles, headings, closing tags, and placeholder replacement.
4. Check annotation anchor/reference/definition matches and identifier collisions.
5. Check attribution details, reusable references, and affected asset/link paths.
6. Review the diff for unintended prose, citation, license, navigation, or path changes.
7. Follow the repository's branch and draft-pull-request workflow. For content
   changes involving custom blocks or annotations, check the GitBook preview when
   available and report the actual verification level.

## Decisions left for later versions

- A fixed warning heading, if the owner wants one; otherwise use descriptive headings.
- Additional page types and conventions as the owner supplies examples.
- Independent rendered verification of the annotation example above.

Older callout mappings in existing pages are not a request for a site-wide migration.
Record future owner-approved conventions here, while retaining source-specific
attribution templates in `attributions.md`.
