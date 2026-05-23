# 01-scan — References

## File-type categories (defaults)
Use these to assign a `type` tag to each file. Override in context.md if needed.

| Category | Common extensions / patterns |
|---|---|
| document | .doc .docx .pdf .txt .md .pages .odt |
| spreadsheet | .xls .xlsx .csv .numbers .ods |
| presentation | .ppt .pptx .key |
| image | .jpg .jpeg .png .gif .svg .webp .heic .tiff .raw |
| video | .mp4 .mov .avi .mkv .m4v |
| audio | .mp3 .wav .aac .m4a .flac |
| code | .py .js .ts .html .css .sh .json .yaml .toml .env |
| archive | .zip .tar .gz .7z .rar |
| system | .DS_Store .tmp .log .bak |
| receipt/invoice | filename contains: invoice, receipt, bill, statement |
| contract | filename contains: contract, agreement, nda, sow, msa |

## Topic/project signals (heuristic)
If a filename contains a proper noun, client name, project code, or year, treat it as a project signal and extract it as a `topic` tag.

## Example inventory row
```
filename: 2024-03-invoice-acmecorp.pdf
type: receipt/invoice
topic: acmecorp
junk-candidate: no
duplicate-candidate: no
notes: —
```
