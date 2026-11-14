# Doce Lar

Working title, from "lar doce lar", home sweet home. The owner's way out of the Apple ecosystem: his own mail, calendar, contacts, notes and reminders, on his own server, with a search that understands what he is looking for.

This repository holds no code. It marks out the goals and points to the projects that do the work.

Status: just started.

## Goals

- **Leave the Apple ecosystem** for mail, calendar, contacts, notes and reminders.
- **Keep the data at home.** The servers run in the owner's home network and are reached from there.
- **A search that works.** The main pain today is finding things in mail and notes. Search covers mail, notes, the documents in the archive and the files on the owner's computers, and an AI helps: it turns a question into queries and sums up what was found.
- **A private AI that can see everything and send nothing.** It reads; it has no tool that sends.
- **A suite of the owner's own applications**, in the long run: mail, calendar, contacts, notes and reminders, joined into one. Desktop first.
- **Mobile later**, on Android or an Android-based system, with an offline mode.

## How to get there

1. **Search first.** A store for the owner's data and helpers that fill it, used through an existing AI client. Mail first, then files, then the document archive.
2. **Off the shelf where it exists.** Calendar and contacts move from iCloud to a server at home and are used with existing programs. Open protocols (IMAP, CalDAV, CardDAV) are the common ground.
3. **A search application of his own**, the first piece of the suite.
4. **His own applications, one at a time**, where the existing ones fall short. They build on the same store.
5. **Mobile**, last.

## Ground rules

- Embeddings are computed at home.
- A language model is reached through an OpenAI-compatible endpoint: local when the hardware allows, otherwise an own key limited to chosen models (zero retention, EU). Later possibly a different endpoint per privacy level.
- Search works without a language model; the model is a layer on top.
- Old notes stay where they are. Nothing is migrated that is not needed.

## Projects

| Project | Part in Doce Lar | State |
| --- | --- | --- |
| [Hausteich](https://github.com/pihme/hausteich) | The store: passive, headless, with a REST interface. Its helpers, the Rinnsale, read mailboxes, folders and the document archive and fill it. | Spec draft, private |
| [RAGite](https://github.com/pihme/ragite) | The search core inside Hausteich: embeddings on the CPU and hybrid search in SQLite. Hausteich is its reference user. | Released |
| [My Data, My Tools, My Rules](https://github.com/pihme/my-data-my-tools-my-rules) | The catalog the off-the-shelf programs are picked from. | Published |
| [Hobelbank](https://github.com/pihme/hobelbank) and [Hermetarium](https://github.com/pihme/hermetarium) | A possible home for the AI that reads the store: a habitat that reaches only the model endpoint. Not decided. | Idea |

Used, not built here: [paperless-ngx](https://github.com/paperless-ngx/paperless-ngx) as the document archive, and [docling-serve](https://github.com/docling-project/docling-serve) as the candidate for turning PDF, office files and pictures into text.

## Open

- The name. "Doce Lar" is a working title.
- Which off-the-shelf servers and programs take over calendar, contacts and mail in step 2.
- Whether the suite is one repository or one per application. To be decided when the second application starts.
- What "AI helps with synchronisation" should mean. Synchronisation itself is left to the protocols.
