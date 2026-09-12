# Publication audit

Independent review on September 12, 2026, covering the final local package build and live-media artifacts. This review reads source, packaged files, screenshots and artifact metadata. It does not start provider sessions, write external documents, publish repositories or repeat the application test suite.

## Package integrity and portability

Each of the three standalone packages contains the same reviewable source and public artifacts. The original approved-save package SHA-256 was recomputed from actual bytes and matched both `publication.json` and the canonical source at that release:

`149c2c96f5bd049834eaa72ae98210ce3175bbb5453057c806d63167156898b8`

All local Markdown links in each package resolve. Every ZIP passes its CRC test, has no absolute or parent-traversal paths, and contains exactly the bytes inspected in its corresponding directory. Startup scripts resolve paths relative to the project; Vite regenerates the SDK runtime from the installed package. The three READMEs disclose one shared codebase and contain screenshots, architecture and artifact links.

## Credentials and private files

Three configured nondefault credential values were privately read from ignored `.env`; a fourth credential value was read from the private Ambiguous CLI store. All were searched as exact bytes in all package files, with zero matches. No credential value was printed or written into this report. Candidate public source and the actual production frontend bundle were also scanned privately with zero matches. A separate credential-shape scan found no embedded private-key, JWT or long literal Bearer credentials in public text source or documentation.

Packages exclude real `.env`, `.ambi`, uploaded rooms, runtime databases, dependency installations, virtual environments, raw logs, Python caches and raw recordings. The example environment file contains empty service-key placeholders. The documented `showroom-local-dev` password is an intentional public default for the Neo4j instance bound to localhost; no custom database password is exempt from scans.

The first prospective Git staging check found raw live footage outside `.gitignore`. This was fixed: both `live-raw` and `live-cdp-raw` are now excluded from Git and packages. `.ambi/` is also ignored and excluded recursively by the builder. Repeated prospective staging checks found zero unsafe paths. These checks used a temporary external Git index without initializing or mutating the workspace.

## Artifact and claim checks

- The final PDF independently parses as exactly five pages.
- The final MP4 independently reports exactly 120.000000 seconds, H.264, 1600 × 900, `yuv420p`, and 11,434,552 bytes. Full decoding passed in [artifact verification](artifact-verification.json).
- The final JPEG poster decodes as 3200 × 1800 and was visually inspected for readability. It shows the actual recorded Orbis result and the illustrative-preview notice.
- Offline inspection of [first direction](../../artifacts/screenshots/live-change-1-final.png) and [second direction](../../artifacts/screenshots/live-change-2-final.png) confirms a deep olive wall and then a cobalt rug, with accepted directions visible. [Live evidence](live-capture.json) separately records advancing decoded frames.
- The generated room visibly drifts in camera position, geometry and furniture details. The current README and [verification record](verification.md) disclose this limitation; persistence claims refer to application constraints and model instructions, not guaranteed visual preservation.
- The first 100 seconds show the actual Orbis session; the final 20 seconds show the later explicitly approved Ambiguous save in the same room. Its returned document was read back and verified; see [save evidence](approved-save.json) and [recovery record](ambiguous-save-recovery.json). The separately labeled recovery recording preserves earlier failures and is not substituted for live-provider evidence.
- [Qoder evidence](qoder.md) records actual authenticated CLI execution, the produced test file, a sanitized transcript and independent passing results. Contract tests are distinguished from live-provider evidence.
- No README or deck claims a prize, DGX hardware execution, customer traction or independent codebases. Cross-event eligibility is already resolved by [participant confirmation](event-eligibility.md).

Public live-session evidence is now a fixed historical report, identical to `live-verification.json`, with the ended-session status clearly recorded. Ongoing browser status is written only to ignored `backend/data/runtime/live-session-status.json`; the package builder excludes it. The archived report and independent review screenshot preserve successful decoded frames and steering evidence.

## Remaining publication boundary

The canonical workspace now has a local Git repository on `main`, initialized with the existing user identity. The first local commit staged 97 public source, documentation and artifact files. Every staged blob was read directly from Git and privately scanned against three configured environment credentials and one Ambiguous CLI credential, with zero matches. Credential-shape checks also found no private-key, JWT or long literal Bearer credentials. All staged entries are regular files; there are no symlinks or path escapes, unsafe private/generated paths, or files over the 95 MB publication threshold. The final demo MP4 is 11,434,552 bytes, below the publication threshold. `git diff --cached --check` passes.

The commit phase uses `git init -b main`, explicit `git add` of public project directories, `git check-ignore` for private paths, a private staged-blob audit using `git ls-files --stage` and `git cat-file blob`, and `git diff --cached --check`. The staged audit is repeated after final documentation and media updates before creating the local commit. The first local commit configured no remote and made no push. The participant subsequently approved the three public repository destinations recorded in [publication status](../publication.md). Their separate publication pass scans actual staged blobs again; commit identifiers are reported separately because a commit cannot contain its own identifier.

Rebuild packages after this report or any other final documentation change. If application source, credentials or artifacts change, repeat their corresponding digest, secret or artifact checks; documentation-only inclusion does not change the backend/frontend digest.

## Approved GitHub publication preparation

The package source manifest now excludes ignored generated `frontend/public/reactor/` assets and TypeScript build metadata. This aligns package source digests with the files actually staged in each standalone repository. Vite regenerates the pinned Reactor runtime during startup/build. All three presentations link the same canonical repository and the other two focused READMEs. The package builder also scans the ignored Ambiguous CLI credential and retains executable script modes. Final repository publication is tracked in [publication status](../publication.md); it does not authorize an Ambiguous write, event entry or social post.

The approved GitHub publication pass successfully pushed all three public repositories and checked each remote `main` reference against its local publication commit. All three standalone staged trees passed exact scans against the four private credentials, source-manifest equality, ignored-path exclusions, regular-file and size checks. See [publication evidence](github-publication.json) for the first public commits. Subsequent documentation commits record the completed publication. The participant later separately approved the exact Ambiguous brief; its actual saved document and read-back are recorded in [save evidence](approved-save.json).

The final approved-save update includes the restricted-visibility fix, uncertain-write reconciliation, five additional recovery tests (23 backend tests passing in total), and the independently verified saved brief. Its 120-second demo and five-page PDF include the actual approved-save result. Source manifests now contain 25 backend/frontend files, including `backend/test_save_recovery.py`; the SHA-256 above covers their final bytes. The publication step again scans canonical and standalone staged blobs and checks package ZIP bytes against committed content before updating the existing public repositories without force pushes.

Final local readiness also passed after the existing Docker/Neo4j instance recovered: frontend HTTP 200, backend health HTTP 200, Neo4j connected, and Ambiguous connected. The [runtime recovery receipt](runtime-recovery.json) records preserved database identity and graph relationships; recovery changed no source files or volumes.

## Fullscreen and voice-search update

The subsequent feature release adds actual Orbis pause/resume, fullscreen direction controls, Exa Amazon discovery and OpenAI transcription. Its canonical backend/frontend source manifest contains 28 files with SHA-256:

`04492bb952b81ecbaeca9bb739b7a614c3ecb862396b5944817b87479bdc03d2`

The current suite passes 33 backend tests. Actual provider receipts, browser checks and screenshots are linked from the [feature verification](voice-and-player.md). The original five-page PDF and two-minute MP4 remain the historical sprint artifacts. Publication rebuilding validates local Markdown links and privately scans all configured credentials; the staged-byte audit and remote tree comparison are repeated for each of the three existing repositories.
