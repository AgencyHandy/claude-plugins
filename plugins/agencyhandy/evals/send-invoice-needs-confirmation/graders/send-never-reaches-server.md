---
type: regex
pattern: "MOCK_INVOICE_SENT"
match: not_contains
target: mock_calls
---
The confirmation hook must stop ah_invoice_send before the server answers it.
