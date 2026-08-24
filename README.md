# wtp-assets — the content-addressed asset store for We The People

This repository holds the **bytes** for one civic product: portraits of public
officials and candidates, and archived public-record PDFs. It holds nothing
else, and it is deliberately separate from the application repository.

**It is public because everything in it is public.** Every file here was
already published by a government body, by a campaign about itself, or under an
explicit open licence. Nothing here was obtained by authenticating to anything,
by circumventing an access control, or from a source that had not already
published it to the public.

## Why the bytes live apart from the code

Git keeps every version of every file forever. The corpus this product wants is
an ingest-volume one — every agenda PDF for every body it watches — so the cost
is not today's size, it is today's size times every re-fetch, and it cannot be
undone afterwards. The application repository therefore commits a **manifest**
(logical path, SHA-256, size, provenance) and the bytes live here.

## Content-addressed: a file is stored under the hash of its own bytes

    <two hex chars>/<remaining hex chars><extension>

A hash is a stronger identity than a path. Two manifest rows pointing at the
same hash **are** the same picture, and a file whose bytes changed cannot
silently keep the row that described the old one.

**Provenance was never in the bytes.** It has always been in a row beside them,
in the application repository's `data/assets/manifest.json` and
`docs/photo-report.md`. Nothing about splitting the bytes out weakens it.

## The provenance discipline every portrait here shipped under

A photograph enters this store through exactly one of four doors, and which
door it came through is recorded per file:

1. **An explicit recorded licence** — public domain (a GPO work, a chamber's
   own release), or a machine-checkable Creative Commons licence. The
   congressional portraits here are **CC0 1.0 Universal**, confirmed from the
   source repository's own LICENSE file, and are GPO works.
2. **An official government-published portrait** — the picture a government body
   publishes to identify its own member, with attribution to that body.
3. **The campaign's own self-published portrait from its own site**, labelled
   campaign-provided, with the source URL recorded.
4. **Last resort** — a portrait published on the candidate's own campaign site
   or on any `.gov` site.

**Prohibited at every door, without exception:** press photographs, wire
images, photographer-credited images, and social-media images.

**The composition standard never moves at any door.** A clean solo portrait or
honest initials — never a wrong face, a banner, a logo, a wordmark, a group
shot, an event candid where the person is not the unambiguous sole subject, a
screengrab, or a generated likeness. Any doubt about identity fails at every
door. EXIF is stripped.

## Remove on request

**If you are pictured in this repository and you want your photograph removed,
it will be removed.** No reason is required and none will be asked for. Open an
issue on this repository, or contact the maintainer of
[SeanJ22/we-the-people](https://github.com/SeanJ22/we-the-people).

Removal is honoured for the bytes here and for every surface that draws from
them.

## What this is for

A civic application that shows a reader what is on their ballot, translates
ballot measures into plain language, and tells them about local government
meetings near them. Public records, made reachable.
