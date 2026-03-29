# CI: Archive annotator-core.jar

## What
Adds an artifact upload step to the `build-with-upload-artifact` job in the CI pipeline.
It uploads `annotator-core/build/libs/annotator-core-*.jar` as a downloadable artifact named `annotator-core-jar`.

## Why
When a patched version of `annotator-core` is needed (e.g., a fix that hasn't been released yet),
this step makes the built jar available for direct download from the GitHub Actions run,
without requiring a full release.

## How to reuse
Cherry-pick commit `d71d2c22` (or the equivalent on this branch) onto any branch where you need
the artifact to be available from the pipeline:

```bash
git cherry-pick ci/archive-annotator-jar
```
