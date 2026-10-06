---
type: regex
pattern: "mcp__plugin_agencyhandy_agencyhandy__ah_(health|whoami)"
match: contains
target: trace
---
Claude must look the workspace up with ah_health or ah_whoami instead of guessing.
