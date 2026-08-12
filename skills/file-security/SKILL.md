---
name: file-security
description: File upload/download, filesystem path, object storage, private media, generated files, MIME/content validation, scanning, signed access, and storage cleanup security.
---


# File and Storage Security

- Treat filenames, paths, MIME types, extensions, metadata, and uploaded bytes as untrusted.
- Prefer server-generated opaque identifiers/object keys.
- Do not place personal data such as names, email, phone, address, or credentials in storage keys.
- Do not trust original filenames for storage paths.
- Keep sensitive storage private by default.
- Authorize each private read/write.
- Use short-lived signed access when appropriate.
- Do not expose storage service secrets to clients.

## Upload Validation

When untrusted uploads are supported:

- allowlist required file types;
- enforce size/count limits;
- verify content/signature/magic bytes where risk warrants it;
- do not trust extension or client MIME alone;
- account for MIME spoofing/polyglot files;
- consider decompression-bomb/archive limits;
- generate destination names server-side.

For high-risk uploads, consider:

- quarantine before activation;
- asynchronous malware scanning;
- fail-closed scan timeout/failure behavior.

## Paths

- Avoid using user input directly as filesystem paths.
- Canonicalize and enforce containment in the intended directory.
- Reject traversal/absolute-path escapes.

## Large Files

Stream large media/files end to end when practical.

Do not load large videos/documents fully into application memory without need.

## Lifecycle

Define cleanup for:

- abandoned uploads;
- replaced objects;
- expired temporary files;
- retention-scheduled data.

Cleanup jobs should be idempotent.

Do not log private signed URLs or sensitive file contents.
