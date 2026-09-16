# Family Companion (Marriage Companion)

Family Companion is a mobile-compatible, Markdown-first Obsidian add-on for short, Christ-centered household checkups. The plugin ID remains `marriage-companion` so it can replace an existing installation without moving your vault data.

## Three focused workflows

- **Family checkup** records the household as a group and only shows family-appropriate areas.
- **Marriage checkup** records the marriage plus two active spouse profiles separately.
- **Kids checkup** lets parents select one or more children and record independent entries for each.

Each step asks for a rating, short answer, current focus, and next step. Scripture prompts remain visible while you work. The wizard is intentionally short and scroll-safe on iOS; one Markdown note is saved for the session.

## Data and compatibility

Records remain under the configured `Marriage Companion/` root:

```text
Marriage Companion/
  Check-ins/
  Members/
  Children/          # legacy child profiles remain readable
  Migration Backups/
```

New check-ins use `type: family-companion-checkin`, `schema_version: 3`, and `checkup_kind: family|marriage|kids`. Older `marriage-companion-checkin` and version-2 records are read as shared legacy checkups and are never guessed into a spouse or child.

Member profiles may be created as `spouse`, `child`, or `other`. Existing child notes are preserved. Managed summaries are refreshed with `Vault.process()` and user-written content outside the managed markers is retained.

## Dashboard

The dashboard provides Family, Marriage, member, and comparison views; transparent rating chips; areas needing care; recent checkups; and separate “Not recorded” states. Use the three start buttons to begin the appropriate workflow, or open a target tab to compare family, marriage, spouses, and children.

## Migration

Migration is explicit. Use **Preview v3 migration**, then **Run v3 migration** from plugin settings or the command palette. A timestamped byte-verified backup and journal are created before records are updated. **Verify migration** reports legacy and v3 records. Restore is intentionally manual so a backup can be reviewed before any replacement.

## Settings

Configure the root folder, default checkup type, spouse requirement, cadence, trend history length, and every area’s order, default rating, checkup mappings, target mappings, Scripture references, and prompt. Empty mappings can be used for a custom area that should appear everywhere.

## Privacy and limitations

The plugin stores ordinary Markdown files and does not encrypt them. It is a personal family reflection tool, not medical, emergency, professional counseling, or diagnostic software. Ratings are conversation prompts, not universal measurements.

## Development

```text
npm ci
npm run typecheck
npm run build
```

The add-on has no network, Dataview, Node-only, or desktop-only dependency and can run without the Red-Beard Dashboard. When Dashboard is installed, Family Companion registers a launcher module and a compact health widget through its public registration API.
