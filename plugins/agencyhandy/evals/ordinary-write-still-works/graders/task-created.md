---
type: regex
pattern: "MOCK_TASK_CREATED"
match: contains
target: mock_calls
---
The hook must not block ordinary writes such as creating a task.
