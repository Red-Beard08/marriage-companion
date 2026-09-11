# Marriage Companion / Family Companion

Marriage Companion is a Markdown-first, Christ-centered family checkup plugin for Obsidian. The compatible plugin ID and root folder remain unchanged, while the workflow now supports whole-family, marriage, and individual-member check-ins.

## Use

Open **Marriage Companion: Open family dashboard**, then choose **Family checkup**, **Marriage view**, or a member tab. A check-in can include one or more targets and records a separate rating, answer, focus, and next step for each selected area. Every check-in is a regular Markdown note under the configured `Marriage Companion/Check-ins/` folder. Add household members with **Add family member**; the legacy **Add child profile** command remains available as a compatibility alias.

Use **Manage family checkup areas** to tailor every check-in area. Each area has a name, display order, default rating for future check-ins, Scripture references, and a custom discussion prompt. Editing an area preserves its stable ID, so past check-in history remains connected; it does not rewrite past notes.

On first load, legacy marriage check-ins are backed up and converted to a clearly labeled shared family target. Existing child notes remain in place and receive a linked copy under `Marriage Companion/Members/`. The migration journal is stored beside the backup. Use **Verify Family Companion migration** to review counts; all migration writes are idempotent and ordinary Markdown remains readable even if a record needs manual repair.

## Limits and care

This plugin stores ordinary Markdown and does not encrypt records. It is not a replacement for pastoral, medical, mental-health, legal, or emergency help. For immediate danger, coercion, self-harm, or safety risk, seek local emergency help.

## Development

Run `npm install`, then `npm test`. Copy `main.js`, `manifest.json`, and `styles.css` into `.obsidian/plugins/marriage-companion/` to install manually.
