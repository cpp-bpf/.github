# Contributing to cpp-bpf

Thank you for your interest in cpp-bpf. This document applies to all
repositories in the cpp-bpf organization unless a repository says
otherwise.

## Before you start

- Read the [vision and scope](VISION.md). Changes outside the scope, such as
  a separate loader or support for the C++ standard library in BPF programs,
  are unlikely to be accepted.
- For anything larger than a small fix, open an issue first so the approach
  can be discussed before you write the code.

## Upstream first

Many problems with C++ in BPF are bugs in clang, libbpf or the kernel. Those
are fixed upstream, not worked around here:

- clang and LLVM: [llvm/llvm-project](https://github.com/llvm/llvm-project),
  label `backend:BPF`
- libbpf and the kernel: the [BPF mailing list](https://lore.kernel.org/bpf/)

If you are not sure where a problem belongs, open an issue here and we will
help find out.

## Pull requests

- Keep each pull request to one logical change, with a commit message that
  explains why the change is needed.
- Add or update tests for the change.
- Make sure CI passes. CI for first-time contributors starts after a
  maintainer approves it.

## Developer Certificate of Origin

All commits must be signed off under the
[Developer Certificate of Origin](https://developercertificate.org/), as in
the Linux kernel. Add a `Signed-off-by` line with your real name and email:

```
git commit -s
```

## AI tools

The use of AI tools is covered by the [Generative AI Policy](AI-POLICY.md).
In short: you are fully accountable for what you submit, and non-trivial use
of AI tools must be disclosed with its
[AI Influence Level](https://danielmiessler.com/blog/ai-influence-level-ail)
(AIL) in the pull request description; maintainers add the matching
`ail:N` label. Do not credit AI tools as authors:
no `Co-Authored-By` or `Signed-off-by` lines for AI tools, as only a human
can certify the DCO.

## Code of Conduct

Everyone participating in cpp-bpf is expected to follow the
[Code of Conduct](CODE_OF_CONDUCT.md).
