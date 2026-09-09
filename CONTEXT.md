# mysociety/fixmystreet context
> refreshed 2026-09-09 | upstream default: master @ d1426634496

## Identity & policies
- upstream: mysociety/fixmystreet, default branch `master`, primary language Perl (Catalyst), English-first (UK English).
- CLA/DCO: none found (no CLA bot, no DCO in CONTRIBUTING/.github).
- AI-assisted PR policy: unstated (no AI_POLICY.md, no AGENTS.md, no AI mention in CONTRIBUTING or PR template).
- signed commits required: no.
- PR template: `.github/pull_request_template.md` (checklist of 7 boxes; fill verbatim, tick only when genuinely satisfied).
- external tracker: GitHub issues + Waffle board (CONTRIBUTING references waffle.io/mysociety/fixmystreet).

## Conventions (verified from merged PRs)
- branch naming: plain kebab-case descriptive names (e.g. `remove-new-badge`, `navbar-tablet`, `dont-include-unconfirmed-alerts-in-csv-count`). CONTRIBUTING: branches starting `NNN-`/`NNN_` or containing `#NNN` auto-move issues to In progress.
- commit style: plain imperative, no Conventional Commits (e.g. "Removed 'New' badge from image report first", "[Dudley] Initial cobrand."). Cobrand-specific commits prefixed `[Cobrand]`.
- test command: `script/test --jobs 3 t` (Perl, via carton). CI = GitHub Actions `default.yml` (perl 5.32.1-5.40.1 matrix). No JS lint in CI (no package.json); `.jshintrc` exists for manual jshint.
- how outside PRs get merged: responsive; many recent external merges (e.g. `remove-new-badge`, `navbar-tablet`). PRs from non-collaborators land in "Current" for triage.

## Maintainer picture
- Active maintainer team (mysociety). Recent merged PRs are mostly cobrand-specific (Sutton, Kingston, CRT, TfL, Dudley) plus small shared fixes.
- Areas actively worked: cobrand rollouts, waste/bulky collections, Open311, geocoding fallbacks. Avoid overlapping in-flight cobrand work.

## Issue-area health
- No "Suitable for Volunteers" issue that is recent + actionable + uncontested survives filters.
- Bug-labeled issues are mostly old (2020-2024). No maintainer-engaged open issue clearly pickable this cycle.

## Gap ledger (dedupe — READ FIRST, never re-pick)
- `2026-09-03` self-found a11y gap: `span.report-a-problem-btn` focusable (`role=button` + `tabindex=0`, from merged PR #4919) but not keyboard-operable (no keydown handler) — outcome: pr-opened (fork PR #1). Lesson: PR #4919 added role/tabindex but forgot the keydown handler; open PR #5184 is styling-only (sass), does not touch it.

## Mined gaps (discovered, not yet attempted)
- `2026-09-03` a11y `span.report-a-problem-btn` has no keydown handler for Enter/Space (WCAG 2.1.1 Keyboard). Repro: focus the span on the report page, press Enter/Space — nothing happens; click works. Expected: Enter/Space triggers scroll-to-top + focus `#pc`, matching the click handler and the dropzone keydown pattern in `web/js/front.js`. Dedupe: merged PR #4919 added role/tabindex only; open PR #5184 is sass styling only. — status: attempted (pr-opened, fork PR #1)
- `2026-09-03` self-found trivial pass (typos + dead links in docs + one cobrand template) — outcome: pr-opened (fork PR #2). Lesson: docs-only, meaning-preserving cleanup; UK dialect respected (colour/behaviour/organise are correct, not typos).

## Mined gaps (discovered, not yet attempted)
- `2026-09-03` typo "propogate/propogating" x3 in docs/customising/integration.md — status: attempted (pr-opened, fork PR #2)
- `2026-09-03` typo "difference scale" + "Pubic Builds" in docs/install/ami.md — status: attempted (pr-opened, fork PR #2)
- `2026-09-03` typo "This pages" in docs/install/vagrant.md — status: attempted (pr-opened, fork PR #2)
- `2026-09-03` typo "it there are" in docs/updating/ami.md — status: attempted (pr-opened, fork PR #2)
- `2026-09-03` typo "untill" in templates/web/peterborough/waste/_service_missed.html — status: attempted (pr-opened, fork PR #2)
- `2026-09-03` dead link MDN truncated URL in docs/customising/css.md — status: attempted (pr-opened, fork PR #2)
- `2026-09-03` dead link mapit.poplus.org in docs/_posts/2012-10-02-easy-install.md + docs/glossary.md — status: attempted (pr-opened, fork PR #2)
- `2026-09-03` dead link transifex projects/p/fixmystreet in docs/customising/language/index.md + docs/_posts/2014-11-20-v1.5.md — status: attempted (pr-opened, fork PR #2)
- `2026-09-03` skipped: fixmystreet.org.au / cuidomiprovincia.diputaciondevalladolid.es (connection failures, possibly temporary) — dropped
- `2026-09-03` skipped: makemyisland.mv (no DNS, but inside a press-release quote) — dropped
- `2026-09-03` skipped: borsetshire.gov.uk image (fictional council placeholder) — dropped
- `2026-09-03` skipped: fr./de./sv./sf.fixmystreet.com (illustrative example URLs in prose) — dropped
