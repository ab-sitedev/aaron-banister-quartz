---
name: Upskill — upstream sync for diverged clone
description: Aaron wants to learn how to sync updates from a parent project into a diverged clone; surface when upskill opportunities are discussed
type: user
---

Aaron wants to learn how to push updates downstream from a parent project (ShadCN Content Catalog) into a variant that was cloned but has since diverged (NBBC Sermon Catalog). He's noted that it might have been better to fork rather than clone from the start.

Surface this when Aaron asks about upskill opportunities, Git workflows, or project architecture decisions involving shared codebases.

**Context:** NBBC Sermon Catalog extends ShadCN Content Catalog but is more experimental. The parent is kept clean/conservative. The clone has diverged enough that a simple pull from upstream isn't straightforward. A fork-based workflow (with `upstream` remote + selective merging or rebase) would be the proper solution to explore.
