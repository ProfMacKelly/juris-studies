# Juris Studies: Prompts for Authoring Through GitHub

**Table of contents**

- [1. A standard opening for most editing tasks](#1-a-standard-opening-for-most-editing-tasks)
- [2. Improve an existing page’s formatting](#2-improve-an-existing-pages-formatting)
- [3. Edit for clarity and student comprehension](#3-edit-for-clarity-and-student-comprehension)
- [4. Turn supplied material into a new page](#4-turn-supplied-material-into-a-new-page)
- [5. Add or revise learning objectives](#5-add-or-revise-learning-objectives)
- [6. Add annotations to difficult passages](#6-add-annotations-to-difficult-passages)
- [7. Apply the correct attribution template](#7-apply-the-correct-attribution-template)
- [8. Reorganize a section or its navigation](#8-reorganize-a-section-or-its-navigation)
- [9. Research a legal issue before changing the text](#9-research-a-legal-issue-before-changing-the-text)
- [10. Verify citations or obtain opinion text](#10-verify-citations-or-obtain-opinion-text)
- [11. Review a GitHub pull request before merging](#11-review-a-github-pull-request-before-merging)
- [12. Publish an approved pull request and verify the result](#12-publish-an-approved-pull-request-and-verify-the-result)
- [13. Audit consistency without starting a large cleanup](#13-audit-consistency-without-starting-a-large-cleanup)
- [14. Make a short follow-up request in an existing authoring chat](#14-make-a-short-follow-up-request-in-an-existing-authoring-chat)
- [Which tools and skills to name](#which-tools-and-skills-to-name)

## 1. A standard opening for most editing tasks

Paste this at the beginning of a new authoring chat, followed by your specific request:

> Work through the GitHub repository `ProfMacKelly/juris-studies`, which is synced with the Juris Studies GitBook site.
>
> Read the current `AGENTS.md`, the Juris Studies authoring style guide, and the relevant navigation entries before editing. If the guide is still unmerged, consult the version in PR #3 and apply its conventions without merging that PR.
>
> Use the GitBook skills appropriate to the task. Inspect the latest repository content and make the changes on a separate task branch. Follow the repository’s draft-pull-request workflow.
>
> Preserve legal substance, quotations, citations, annotations, attributions, licensing, and published paths unless my request calls for changes. Return the pull request link, GitBook preview link when available, and the checks performed. Leave the changes unmerged.

You do not need to repeat this in every message within the same chat. Follow-up instructions can be brief.

## 2. Improve an existing page’s formatting

**Skill:** `write-docs`
**Access:** GitHub plugin for inspection; repository tools for changes.

> Use write-docs to improve the formatting of [page link or repository path].
>
> Preserve the wording and legal substance. Improve headings, lists, and paragraph organization, and use the Juris Studies callout conventions where the content supports them.
>
> Preserve existing annotations and attribution blocks. Prepare a draft pull request and identify any suggested substantive edits separately.

Use this when you want presentation changes without a rewrite.

## 3. Edit for clarity and student comprehension

**Skill:** `write-docs`

> Edit [page] for undergraduate readers using write-docs. Improve sentence clarity, define unfamiliar terms where the source supports a definition, and reduce unnecessary repetition.
>
> Preserve the legal rules, qualifications, quotations, citations, and annotations. Do not add unsupported legal propositions. Flag passages that need research or my judgment.
>
> Prepare a draft pull request. In its description, distinguish wording changes from any proposed changes to substance.

Use this when rewriting is authorized but legal accuracy needs particular care.

## 4. Turn supplied material into a new page

**Skill:** `write-docs`

> Use write-docs to turn the attached material into a new Juris Studies page in [folder or section].
>
> Follow the authoring guide. Include a short introduction, learning objectives, clear headings, and appropriate annotations or callouts. Base the content on the supplied material and identify gaps instead of filling them with invented information.
>
> Select the applicable attribution template from attributions.md. Update SUMMARY.md in the appropriate place and check affected links and assets. Prepare a draft pull request.

Provide the source material and its source or licensing information when known.

## 5. Add or revise learning objectives

**Skill:** `write-docs`

> Read [page or lesson folder] and propose four to six learning objectives that match what students actually encounter.
>
> Use observable actions such as identify, distinguish, explain, or apply. Avoid objectives that promise skills the lesson does not teach.
>
> Add them using the Juris Studies Learning Objectives callout. Prepare the repository changes for review.

If you want to approve the objectives before they are inserted, replace the final sentence with:

> Show me the proposed objectives here before editing the repository.

## 6. Add annotations to difficult passages

**Skill:** `write-docs`
**Optional research:** LawDiver skills when annotations require new legal authorities.

> Use write-docs to add annotations to [page] for terms or passages likely to confuse undergraduate readers.
>
> Use the Juris Studies linked-text annotation pattern. Preserve existing identifiers, choose unused identifiers for new annotations, and place matching definitions at the bottom of the file.
>
> Keep annotations concise and relevant to the surrounding text. Use the existing sources where sufficient; flag anything requiring additional research.
>
> Check the references and definitions, and test the annotation interaction in the GitBook preview if accessible. Report what you actually verified.

## 7. Apply the correct attribution template

**Skill:** `write-docs`

> Review the source information for [page] and select the appropriate template from attributions.md.
>
> Complete the attribution using the actual source title, author, source URL, and stated license. Preserve the appropriate expandable heading and badge formatting, and adjust relative asset paths for this page’s location.
>
> Preserve applicable reusable-content references. Flag missing or conflicting information instead of guessing. Prepare a focused draft pull request.

For mixed-source pages, add:

> Identify which portions come from which sources and include the applicable attributions for each.

## 8. Reorganize a section or its navigation

**Skills:** `configure-site` and `write-docs`

> Use configure-site and write-docs to inspect [section or folder] and its SUMMARY.md entries.
>
> Propose a clearer reading order for students. Show the current and proposed outlines, explain the educational reason for each move, and identify affected page addresses and links.
>
> Give me the proposal before making structural changes.

After agreeing on the outline:

> Implement the agreed outline through the repository. Preserve existing page paths where possible, update affected links and navigation, and identify any redirects needed. Prepare a draft pull request.

## 9. Research a legal issue before changing the text

**Plugin:** LawDiver
**Skill:** `caselaw-research`
**Then:** `write-docs`

> Use LawDiver’s caselaw-research skill to research [specific issue] in [jurisdiction and relevant courts].
>
> Focus on [date range or doctrinal question, if applicable]. Provide relevant authorities with citations and explain their relevance. Report available treatment signals and their limitations.
>
> Compare the findings with [repository page]. Propose any needed corrections before editing it.

Always name the jurisdiction. “Federal law” may still require identifying the relevant circuit or whether you want Supreme Court authority.

## 10. Verify citations or obtain opinion text

**Plugin:** LawDiver
**Skills:** `check-citation-good-law` or `retrieve-opinion`

For citation checking:

> Use LawDiver’s check-citation-good-law skill to verify the case citations in [page].
>
> Report whether each citation matches an authority and what treatment information is available. Separate a citation-format issue from a possible problem with the proposition it supports.
>
> Give me the findings before changing the page.

For opinion text:

> Use LawDiver’s retrieve-opinion skill to obtain [case name and citation]. Locate the passages addressing [issue] and provide accurate pinpoint references.
>
> Compare those passages with the quotation or summary in [page]. Propose corrections, preserving the distinction between the court’s text and our editorial annotations.

For statutory or court-rule text, name the `retrieve-statute` skill and provide the citation and jurisdiction.

## 11. Review a GitHub pull request before merging

**Access:** GitHub plugin and repository tools
**Skill:** `write-docs` for GitBook-specific checks.

> Review GitHub pull request [link] against the Juris Studies authoring guide and repository workflow.
>
> Check for accidental changes to legal meaning, lost citations or annotations, incorrect callout styles, incomplete attributions, broken links, missing assets, and navigation problems.
>
> Inspect the GitBook preview if available. Report actionable findings with file locations and distinguish source checks from rendered checks. Keep the review here in chat; do not post comments or merge.

Use this for a **GitHub pull request**. The `cr-review` skill is specifically for **GitBook change requests**.

## 12. Publish an approved pull request and verify the result

**Access:** GitHub/repository tools; GitBook tools or browser for verification.

> Merge the approved GitHub pull request [link] after checking its current changes, review status, conflicts, and relevant checks.
>
> Then verify that GitBook has synchronized the merged revision. Check the affected public pages, including [specific callouts, annotations, links, or navigation].
>
> Report the merge result, synchronization status, and what you verified on the live site. If a problem prevents completion, explain the actual blocker.

This prompt authorizes publication. Use it when you are ready for the changes to reach the site.

## 13. Audit consistency without starting a large cleanup

**Skills:** `write-docs`; `configure-site` if navigation is included.

> Audit [folder or section] against the Juris Studies authoring guide.
>
> Inventory inconsistent callout styles, malformed annotation references, incomplete attribution placeholders, broken relative asset paths, and navigation mismatches.
>
> Give me a prioritized report with representative examples. Separate mechanical repairs from changes needing editorial judgment. Do not edit files yet.

Then limit the implementation:

> Fix the mechanical problems identified in items [numbers]. Leave the judgment-dependent items for later. Prepare a focused draft pull request.

## 14. Make a short follow-up request in an existing authoring chat

Once the repository, guide, and review workflow are established, prompts can be simple:

> Add a Law in Practice callout applying this rule to a small-business scenario. Keep it consistent with the sources already on the page.

> Convert this explanation into an annotation on the phrase “subject-matter jurisdiction,” preserving the existing note identifiers.

> Use the relevant attribution template and check that its badge path works from this folder.

> Review the latest draft for changes in legal meaning before we publish.

> Address the review findings and update the same pull request. Leave it unmerged.

## Which tools and skills to name

| Task | Useful tools or skills |
|---|---|
| Write, format, or repair GitBook pages through repository files | `write-docs` |
| Reorganize navigation or site structure | `configure-site` with `write-docs` |
| Inspect repository content and GitHub pull requests | GitHub plugin |
| Make repository changes, commits, and branches | Local Git tools, following `AGENTS.md` |
| Work directly with a GitBook change request | `cr-create` or `cr-review` |
| Research cases or verify authorities | LawDiver and its relevant research/retrieval skill |
| Document a software API | `write-openapi` |
| Develop a custom GitBook integration | `build-integration` |

For ordinary Juris Studies authoring through GitHub, start with **`write-docs`, the repository guide, and a focused request**. Add other skills when the task calls for their capabilities.
