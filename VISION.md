# cpp-bpf project direction, vision, and scope

cpp-bpf is an open source project to make C++ a practical and reliable
language for writing BPF programs. The vision of cpp-bpf is that choosing
C++ for a BPF program is as safe and well supported as choosing C, whether
the program is a weekend experiment, part of a production system, or a
component of another open source project.

cpp-bpf does not aim to support all of C++ in BPF programs. The goal is that
the C++ that fits the BPF execution model, such as classes, templates,
inheritance and RAII, works as reliably as C: it compiles without crashing,
gets correct CO-RE relocations, and produces BTF that the kernel accepts.

BPF programs today are written almost exclusively in C. C++ compiles to BPF
in principle, but in practice it has been unreliable: clang crashed on common
C++ records when emitting BTF, CO-RE relocations into C++ records could
silently get wrong offsets, and the libbpf headers and documentation assume
C. At the same time, C++ has clear benefits for BPF code: templates in place
of macros, stronger compile-time checks, RAII for locks and kernel objects,
and headers that can be shared with C++ userspace code.

cpp-bpf builds on the existing BPF ecosystem rather than replacing it. The
project does not provide its own loader or a replacement for libbpf; libbpf
already works from C++, and cpp-bpf uses it. C and C++ BPF code use the same
`vmlinux.h`, the same libbpf headers and the same object files, so existing
projects can adopt C++ gradually.

The cpp-bpf project aims to serve BPF developers, from individual
contributors to teams running BPF in production, by providing:

* Upstream support for C++ in clang, libbpf and the kernel, so that C++ BPF
  programs work with stock toolchains, without special flags or workarounds
* A small library for the BPF side of a program: RAII wrappers, typed maps,
  and thin wrappers over helpers and kfuncs, with no runtime cost compared to
  equivalent C
* A thin C++ layer over libbpf and its skeletons for userspace
* A project template, documentation and examples for common program types
  such as XDP, tc and tracing
* Continuous testing across supported kernel and clang versions

## Principles

* **Upstream first.** Problems in clang, libbpf or the kernel are fixed in
  those projects, not worked around in cpp-bpf.
* **Zero cost.** A C++ BPF program should compile to the same instructions as
  the equivalent C program.
* **Interoperable with C.** C++ support never requires changes to C code or
  to existing BPF tooling.

## Out of scope

* A replacement for libbpf or a separate loader
* The C++ standard library, `new` and `delete`, or C++ exceptions in BPF
  programs; BPF exceptions (`bpf_throw`) are in scope
* Rewriting existing C BPF projects in C++
* Kernel changes made only for this project

## Requirements

* C++20
* clang; GCC may follow once its BPF backend is tested with C++
* Linux from the oldest maintained LTS release (currently 6.1); features that
  need newer kernels are used only where the running kernel supports them

## Roadmap

1. Compiler support: BTF and CO-RE for C++ records in LLVM (in progress)
2. libbpf headers usable from C++: `SEC()`, `BPF_CORE_READ()`, `BPF_PROG()`
   and kfunc declarations
3. First library release with examples
4. First users outside the project
