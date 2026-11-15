# IsoKron pre-registrations

IsoKron records the SHA-256 hash of a study design in this repository before the study's confirmatory data are collected. The design is published in full with the results. Anyone can then hash the published design and compare it with the record made here.

| Record | Recorded (UTC) | Subject |
|---|---|---|
| [2026-001](records/2026-001.md) | 15 November 2026 | Design of a controlled experiment on how AI agents respond to tool results |

## What a record contains

- The SHA-256 hash of the frozen design document, in a `.sha256` file in the format `sha256sum` writes.
- The date of the record. The commit that adds a record is signed by GitHub and carries GitHub's time.
- RFC 3161 timestamp tokens over the `.sha256` file from two independent timestamp authorities, base64-encoded.
- A statement of what data, if any, existed when the record was made.

## Amendments

A design that changes before its data are collected gets a new record with a new hash. The new record names the one it replaces and says what changed. Records are never edited or removed.

## Checking a record

When a design is published:

```
sha256sum 3-design.md        # compare with records/<id>.sha256
base64 -d records/<id>.<authority>.tsr.b64 > token.tsr
openssl ts -reply -in token.tsr -text        # shows the time and the hash that was stamped
sha256sum records/<id>.sha256                # compare with the stamped hash
```

IsoKron is a trading name of Stormhaven Enterprises LLC. Contact: https://isokron.ai
