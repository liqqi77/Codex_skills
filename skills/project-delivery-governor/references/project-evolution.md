# Project Evolution and Durable Lessons

This reference captures reusable lessons from successive versions without turning historical implementation details into universal rules.

## What the Versions Taught

### The first delivery established role independence

The earliest complete flow separated requirements and contract decisions, implementation, independent review, specialist testing, and human acceptance. Its durable contribution was clear responsibility and independent evidence. Its weakness was that every small change could inherit the full chain even when the risk did not justify it.

### Reliability work exposed governance inflation

The next reliability-focused phase introduced finer task states, more sub-stages, artifact identity checks, and incident handling. These controls helped with concurrency and recovery, but they also became a competing project: teams spent time proving orchestration state, repeating reviews, and repairing evaluation tools while the user-visible problem remained unresolved.

The lesson is not to remove reliability. It is to attach every control to a concrete risk and a downstream decision.

### Architecture work clarified useful boundaries

Later versions separated application orchestration, unit-of-work behavior, tools, models, and external integrations. The valuable result was stable responsibility and testable contracts. The risk was treating abstraction itself as progress. A module boundary is justified only when it makes a current product change safer, clearer, or independently testable.

### Natural-language and data versions favored consolidated quality

As user-facing and data-management capabilities matured, implementation tasks became broader product slices and independent review plus testing was consolidated. This reduced handoffs while preserving quality. It established the default pattern: one implementation owner, one independent quality owner, and human acceptance for visible behavior.

### Image, space, and mobile work restored the user journey

Image import, hierarchical spaces, and mobile/device flows revealed that technically present capabilities can still be unusable. Missing upload paths, awkward location selection, incomplete correction actions, and pairing-only screens showed why acceptance must exercise the whole user task rather than count endpoints or pages.

### Voice work showed how evaluators can hijack the roadmap

Work intended to improve voice experience drifted into diagnosing launchers and evaluation infrastructure. The supporting tool failure was real, but it was not the user's core product problem. The durable rule is to allow one bounded tool check, then continue with direct product evidence or record the tool separately.

## Stable Rules

1. One active version has one user-visible objective and one authoritative board.
2. State the affected user scene before naming internal causes.
3. Freeze the smallest complete product slice, not the smallest code edit.
4. Use LEAN by default and add gates only for named risk.
5. Preserve independence between implementation and the quality conclusion.
6. Merge review and targeted testing unless a specialist risk requires separation.
7. Require human acceptance for interaction and wording claims.
8. Repair the earliest confirmed divergence, not every downstream symptom.
9. Stop after two no-information probes or two ambiguous rework rounds.
10. Keep tools, evaluators, session mechanics, hashes, and status fields subordinate to product decisions.
11. Separate current blockers, current non-blockers, future work, and tool issues.
12. Stop at the authorized gate; do not silently start the next version or external action.

## Practices to Retire

- assigning a separate role to every document or tiny check;
- using model names as organizational roles;
- requiring full-project regression after every local change;
- rerunning unchanged tests to create confidence by volume;
- treating a worker's completion message as gate approval;
- using hashes as generic correctness evidence;
- maintaining several current-status files with overlapping truth;
- allowing internal defects to displace agreed roadmap work;
- building elaborate state machinery for a single synchronous task;
- reporting internal codes before explaining user impact.

## How to Adapt This History

Carry forward the principles, not the old number of stages. For each new project, begin with the user journey and risk profile, select the minimum roles and evidence, and add stricter controls only when the decision cost justifies them.
