## cpp-bpf

[![Vision](https://img.shields.io/static/v1?label=Vision&message=and%20Scope&color=blue)](https://github.com/cpp-bpf/.github/blob/main/VISION.md)
[![Contributing](https://img.shields.io/static/v1?label=Contributing&message=Guide&color=brightgreen)](https://github.com/cpp-bpf/.github/blob/main/CONTRIBUTING.md)
[![Governance](https://img.shields.io/static/v1?label=Governance&message=and%20Maintainers&color=yellow)](https://github.com/cpp-bpf/.github/blob/main/GOVERNANCE.md)
[![AI Policy](https://img.shields.io/static/v1?label=Generative%20AI&message=Policy&color=blueviolet)](https://github.com/cpp-bpf/.github/blob/main/AI-POLICY.md)
[![Discussions](https://img.shields.io/static/v1?label=GitHub&message=Discussions&color=orange)](https://github.com/cpp-bpf/cpp-bpf/discussions)
[![Code of Conduct](https://img.shields.io/static/v1?label=Code%20of&message=Conduct&color=red)](https://github.com/cpp-bpf/.github/blob/main/CODE_OF_CONDUCT.md)

cpp-bpf is an open source project to make C++ a practical and reliable
language for writing [BPF](https://ebpf.io/) programs, building on clang and
libbpf rather than replacing them.

### Status

The project is at an early stage and has no release yet. The library,
examples and build rules are in
[cpp-bpf/cpp-bpf](https://github.com/cpp-bpf/cpp-bpf). It needs a clang
with a BTF fix for C++ records that is under review in LLVM; the
[tracking issue](https://github.com/cpp-bpf/cpp-bpf/issues/4) lists this
and the other upstream work.

### Community

cpp-bpf is open to anyone who wants to use or improve C++ for BPF. Read the
[project vision](https://github.com/cpp-bpf/.github/blob/main/VISION.md) to
see where we are going, and the
[contributing guide](https://github.com/cpp-bpf/.github/blob/main/CONTRIBUTING.md)
to get started.

- Questions, ideas and things you built: [Discussions](https://github.com/cpp-bpf/cpp-bpf/discussions)
- Bugs and concrete proposals: [issues](https://github.com/cpp-bpf/cpp-bpf/issues)
- Current upstream work: [tracking issue](https://github.com/cpp-bpf/cpp-bpf/issues/4)
- Writing BPF programs in C++? Add yourself to [USERS.md](https://github.com/cpp-bpf/cpp-bpf/blob/main/USERS.md)
