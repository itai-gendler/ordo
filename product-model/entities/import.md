---
domain: data
references:
- kind: code
  role: implementation
  target: apps/server/src/import-export/import.service.ts#ImportService
---

# Import

One upload of a bookmarks file, from reading the file through its preview to the saved result.

## Information kept

- **File name** — the uploaded file's name
- **Format** — ordo JSON, browser bookmarks HTML or CSV, detected from the file
- **New bookmarks** — how many links in the file are new to the library
- **Already saved** — how many links in the file are already in the library
- **Skipped rows** — rows that could not be read, with sample reasons
- **New folders** — folders the import will create
- **Locked folders** — existing locked folders the file would import into
- **Duplicate handling** — Skip, Update or Add copies for links already saved
- **All at once** — whether the import saves everything or nothing
- **Imported** — how many bookmarks were added
- **Updated** — how many saved bookmarks were updated
- **Failed rows** — rows that could not be saved, with reasons
- **Problem** — why the import failed

## States

### Reading file

The file is being read.

### Ready

The preview is ready and waits for the Account holder to confirm.

### Saving

The bookmarks are being saved.

### Complete

The import finished; its result is shown.

### Failed

The file could not be read or the import could not be saved.
