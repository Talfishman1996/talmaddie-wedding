# Wedding Planning - Vendor Research Project

## Overview
Wedding vendor research and comparison project. Contains detailed analysis of 172 vendors across 10 categories.

## Key Files
- `MASTER-VENDOR-SUMMARY.md` - Complete guide with top picks and budget
- `vendor-comparison-*.md` - Detailed category comparisons
- `wedding-vendor-guide-iphone.html` - Interactive mobile guide

---

## Tools Available (From Global Config)

### Memory System
| Situation | Tool | Example |
|-----------|------|---------|
| Starting session | MCP Memory | `mcp__memory__open_nodes` names=["Wedding_Planning"] |
| Storing vendor info | MCP Memory | `mcp__memory__add_observations` |
| Finding past research | Recall | `/recall "florist options"` |

### Browser Automation (Chrome DevTools PRIMARY)
For vendor website research:
```
mcp__chrome-devtools__take_snapshot
mcp__chrome-devtools__navigate_page
```

**Secondary:** Browserbase (if Chrome unavailable)

### Autonomous Mode
For multi-vendor research tasks:
```
/ralph-loop "Research [CATEGORY] vendors" --max-iterations 20
```

---

## Parallel Agent Safety

**Critical:** This project has ONE main HTML file (`wedding-vendor-guide-iphone.html`).

| Task Type | Allowed |
|-----------|---------|
| Multiple agents editing HTML | NO - Sequential only |
| Multiple agents researching vendors | YES - Different targets |
| Agent editing HTML + agent researching | YES - Different targets |

**Lesson learned:** On 2026-01-11, 5 parallel agents editing the same HTML file caused data loss (172 vendors → 76). Always run SEQUENTIAL when targeting `wedding-vendor-guide-iphone.html`.

---

## Project Notes
- Wedding date: September 2026
- Venue: Los Robles Golf Course, Thousand Oaks, CA
- Guest count: ~40
- Budget documented in MASTER-VENDOR-SUMMARY.md
