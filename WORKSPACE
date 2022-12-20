workspace(name = "cxx.rs")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_rust",
    sha256 = "edb87c0d2ba70823fe3df7862676d695599314a4634b9758bd55f0e8f19c2751",
    urls = ["https://github.com/bazelbuild/rules_rust/releases/download/0.4.0/rules_rust-v0.4.0.tar.gz"],
)

load("@rules_rust//rust:repositories.bzl", "rules_rust_dependencies", "rust_register_toolchains")

RUST_VERSION = "1.66.0"

rules_rust_dependencies()

rust_register_toolchains(
    version = RUST_VERSION,
)

load("//tools/bazel:vendor.bzl", "vendor")

vendor(
    name = "third-party",
    cargo_version = RUST_VERSION,
    lockfile = "//third-party:Cargo.lock",
)
