# Clark Labs shared workflows

This public repository is the organization-wide authority for reusable CI.
Satellite repositories should contain only a thin caller workflow and pin the
reusable workflow to a full commit SHA.

Available gates:

- `rust-library.yml`: pinned Rust, kache, format, build, clippy, nextest,
  doctests, documentation, and dependency-policy gates for Rust libraries.
- `rust-research.yml`: dependency build and compiler smoke for Rust research.
- `python-research.yml`: dependency-free Python syntax smoke for research repos.
- `zig-library.yml`: checksum-pinned Zig 0.16.0 build and test gate.

Callers may override the working directory and gate commands when a repository
has a stronger native contract. Overrides run with read-only GitHub token
permissions and receive no secrets.

New Rust repositories should start from the `clark-rust-template` cargo-generate
template. The organization workflow template then pins this reusable workflow
to an exact commit so the repository has the same required gate from day one.
