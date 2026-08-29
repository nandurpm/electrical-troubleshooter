# Src

## Purpose

Contains the production implementation of Electrical Troubleshooter: command handling, domain rules, storage, reports, and local serving as applicable.

## Contents

- `cli.mjs` — Implements Electrical Troubleshooter's command-line interface and coordinates validation, persistence, report generation, and local serving.
- `examples.mjs` — Provides validated troubleshooting-tree examples used to demonstrate Electrical Troubleshooter's diagnostic workflow.
- `model.mjs` — Defines Electrical Troubleshooter's domain model, validation rules, calculations, and aggregation helpers.
- `report.mjs` — Builds Electrical Troubleshooter's self-contained report artifacts and browser-side interactions from validated data.

## Responsibilities

Production behavior belongs here. Generated reports, user data, and repository documentation should remain outside this folder.

## Important Notes

- This folder is part of **Electrical Troubleshooter** and should be kept consistent with the commands and architecture documented in the root README.
- Paths and file roles listed above reflect the current repository implementation.

