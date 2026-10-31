<p align="center"><img src="assets/benz-books.svg" alt="Benz Book Publisher" width="800"></p>

# Benz Book Publisher

Turn a manuscript into a consistent, checked release for **IngramSpark or Amazon KDP** with Codex.

This skill guides editing, book layout, full-image cover design, release checks, and authorized submission. It keeps each platform's files and each edition's publishing decisions separate.

For example: give Codex a picture-book manuscript and ask for an IngramSpark paperback package. The workflow calls for centered, naturally broken text, artwork that fills the cover, an official template based on final pagination, and a record of what was actually checked.

## Start with Codex

Copy this request into Codex:

```text
Use skill-installer to install publish-ingramspark-kdp from
https://github.com/Benz4000/benz-book-publisher/tree/main/publish-ingramspark-kdp
Preserve an existing installation and ask before replacing it.
```

This is an installation request, not an automatic installer. Codex must have its skill-installer available and network access. Review any requested permissions. The package does not install a browser, publishing software, or account integrations.

Prefer downloading files yourself? See [Manual installation](INSTALL.md), including the versioned ZIP and copy commands.

After installation, start a request with:

```text
$publish-ingramspark-kdp
Prepare this manuscript for KDP paperback and Kindle.
Keep my listed author and existing edition records. Prepare files for review;
do not submit until I authorize it.
```

## What it checks

- Justified ordinary prose and back-cover copy with natural final lines; no isolated last word or artificial spacing fixes.
- Centered picture-book text with deliberate phrase-based line breaks.
- Full-image fronts with title and author typography composed into the artwork.
- Separate official templates and files for each platform and print format.
- Complete editorial reads, rendered visual checks, EPUB validation, and truthful review coverage.
- Exact revision hashes and distinct upload, validation, submission, proof, distribution, and live states.

It preserves originals, resumes existing profiles, and checks account state before retrying uncertain submissions. It keeps proof approval, distribution changes, and payment within their actual authorization.

## What you need

A skill-capable Codex environment, your manuscript and rights information, and the tools needed for your requested output. PDF rendering, EPUBCheck, image tools, and authenticated platform access are separate prerequisites when the task needs them. This is a workflow skill, not bundled typesetting or publishing software. It does not guarantee platform acceptance, professional language review, or physical print quality.

## Compatibility

| Environment | Status |
| --- | --- |
| Codex | Package structure, relative references, privacy scan, and ZIP contents checked on October 31, 2026. Public-package installation and an end-to-end publishing run have not been tested. |
| Other skill-capable assistants | Unknown; no compatibility or installation claim is made for this package. |

Browser and account operations depend on the host's supported tools and permissions. Codex invocation syntax and controls should not be assumed to work in other products.

## Privacy and scope

The public package excludes private collection profiles, personal contact details, local machine paths, account identifiers, manuscripts, and chat handoffs. Use [the project-profile guide](publish-ingramspark-kdp/references/project-profile.md) to record your own decisions privately.

The skill grants no account access or publishing permission. Keep private project records outside this repository. No license has been selected for this publication.

Independent Benz project. Not affiliated with or endorsed by Amazon, IngramSpark, or OpenAI.
