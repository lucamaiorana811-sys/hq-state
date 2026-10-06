# hq-state

Laufzeit-Zustand von HQ (privat). Einziger Schreiber: GitHub-Workflow `hq-tick` im Repo `hq`
(concurrency-Gruppe `hq-runtime`). Nicht von Hand committen.

- `hq.sqlite3` – State Store (Tasks, Runs, Leases, Workflows, Ereignisse; append-only Historie)
- `runtime_state.json` – Vertrag `hq.runtime_state/1` (abgeleitet, keine eigene Wahrheit)
- `events.jsonl` – lesbarer Export aller Ereignisse
- `KILL` – existiert diese Datei, tut jeder Tick nichts (Kill-Switch)

Keine Klartext-Inhalte im Export; der Store selbst enthaelt Agent-Outputs (Slice 1: nur Mock-Daten).
