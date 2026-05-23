# 02-design — References

## Folder tree patterns

### Pattern A: Project-first (default)
```
projects/
  acmecorp/
    invoices/
    contracts/
    assets/
  personal/
    finances/
    photos/
archive/
  2023/
  2024/
```

### Pattern B: Type-first
```
documents/
  invoices/
  contracts/
  reports/
images/
  screenshots/
  photos/
code/
archive/
```

### Pattern C: Date-first (suitable for logs, receipts, journals)
```
2024/
  01-january/
  02-february/
2025/
  01-january/
```

## Naming convention examples
| Raw name | Cleaned name |
|---|---|
| Copy of Invoice March.pdf | 2024-03_invoice-acmecorp_v1.pdf |
| FINAL FINAL report.docx | report-q1-review_final.docx |
| untitled 3.txt | (flag for deletion) |
| Screenshot 2024-01-15.png | (flag for deletion or rename to context) |

## Depth rule of thumb
- Max 3 levels deep for a personal collection.
- Max 4 levels for a professional/client collection.
- Deeper = hard to browse; use filename detail instead.
