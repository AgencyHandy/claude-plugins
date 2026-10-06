---
type: regex
pattern: "mcp__plugin_agencyhandy_agencyhandy__ah_[a-z_]*(create|update|send|delete|set_status|assign|invite|convert|set_values)"
match: not_contains
target: mock_calls
---
A read question must not even attempt a write tool.
