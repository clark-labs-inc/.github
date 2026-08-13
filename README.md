# Clark Labs shared workflows

This public repository is the organization-wide authority for reusable CI.
Satellite repositories should contain only a thin caller workflow and pin the
reusable workflow to a full commit SHA.

Available gates:

- `rust-library.yml`: build, tests, and doctests for Rust libraries.
- `rust-research.yml`: dependency build and compiler smoke for Rust research.
- `python-research.yml`: dependency-free Python syntax smoke for research repos.
- `zig-library.yml`: checksum-pinned Zig 0.16.0 build and test gate.

Callers may override the working directory and gate commands when a repository
has a stronger native contract. Overrides run with read-only GitHub token
permissions and receive no secrets.
