# Smart Campus Room Availability Checker

A static, client-side reference implementation of the fictional Room SE-101 availability checker for Software Engineering Practice 12.

**Public Bolt demo:** https://smart-campus-room-ch-1wck.bolt.host/

This repository provides an inspectable HTML source snapshot with matching inputs, fictional booking data, decision rules, acceptance cases, and two views. It is a clean reference implementation of the demo behavior, not a byte-for-byte export from Bolt.

## Run locally

The page uses an inline JavaScript module. Serve the repository over HTTP instead of opening the file directly. For example: python3 -m http.server 8080. Then open http://localhost:8080 and select Run all 8 acceptance tests in either view.

## Views

- **Code-based** shows the form, read-only booking list, decision rules, and test runner.
- **Low-code simulation** presents the same workflow as configuration cards. It is not an Appsmith, Budibase, TeleportHQ, or Power Apps application, and it is not independent evidence from a low-code platform.

Both views share the same client-side rule function. Tests use a fixed clock of 24 November 2026 at 10:00 so the past-start case is repeatable. The live form uses the browser's current time.

## Prototype limits

All booking data is fictional and fixed in memory. The page has no backend, account flow, external dependencies, network calls, persistence, or production reservation feature. Do not enter personal or real booking data.

Acceptance cases are built into the app. The report documents their expected and observed results.
