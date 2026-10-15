---
name: workshop-get-started
description: Testing knowledge for the Get started with workshops tutorial in docs/tutorial/part-1-get-started.rst.
---

# Get Started With Workshops

## Intended Audience

The reader knows basic Linux shell commands, Git, and YAML but is new to
Workshop, SDKs, and Ollama.
Test only this first tutorial part, not the linked follow-up tutorials.

## Environment And Prerequisites

- The test runs on a disposable Ubuntu runner with snap, sudo, and LXD prepared
  by the caller workflow. Follow the tutorial's LXD refresh branch when LXD is
  already installed; the install and refresh examples are alternatives, not
  consecutive steps.
- Install the Workshop snap as documented. Test the published snap, not a local
  build from the checked-out source tree.
- Git must be available. It may be installed as a reader prerequisite if absent;
  record any prerequisite installation in the report.
- Network access is needed for snaps, LXD images, the SDK Store, and the
  TinyLlama model download. Downloads can take several minutes.
- GPU hardware is not assumed. Start with the documented `cpu/stable` channel
  and still test the later switch to `vulkan/stable` exactly as written; do not
  silently change the channel to work around a failure.

## Reading The Tutorial

- This is reStructuredText. In `console` blocks, `$` and
  `workshop@dev:/project$` are prompts, not part of the commands. Unprompted
  lines are expected output, not commands to execute.
- Follow prose instructions too. YAML blocks captioned `.workshop/dev.yaml`
  describe the file to inspect or edit at that point in the tutorial. Do not
  execute YAML as shell commands or apply later examples early.
- Keep the working directory across commands, including after entering
  `ollama-python-project`. Create that project under the clean run directory,
  not in the checked-out documentation repository.
- Commands following `workshop shell` run inside that shell until `exit`.
  Use an interactive terminal when available. For `ollama run tinyllama`, wait
  for the model download and console to become ready before sending Ctrl+D.
  If the tester cannot drive an interactive session, report that limitation
  rather than claiming the step succeeded or silently substituting a command.
- Sphinx roles, substitutions such as `|ws_markup|` (Workshop), reference
  labels, and `.. @artefact` / `.. @tests` comments are documentation markup,
  not reader commands. Links to reference material do not extend the test to
  other tutorials.

## Known Acceptable Variations

- SDK versions, revisions, available channels, sizes, model IDs, timestamps,
  durations, absolute host paths, and Ubuntu point releases can change.
  Compare their meaning rather than requiring the sample values verbatim.
- The expected base changes from Ubuntu 22.04 to Ubuntu 24.04 after refresh.
  These releases, the selected SDK channels, and the workshop's usable state
  are meaningful expectations, not cosmetic variations.
- `sdk find` may return additional matches, and `sdk list` may retain older
  SDK revisions after refresh, as the tutorial explains.
- Use the actual refresh change ID from `workshop changes` if it differs from
  the illustrative `4` in `workshop tasks 4`; record the substitution in the
  steps performed. The tasks must correspond to the refresh being inspected.

No other deviations are pre-approved. Record broken commands, missing setup,
or incorrect meaningful output instead of repairing the tutorial silently.
Use the action's shared tester instructions for the result and report format.
