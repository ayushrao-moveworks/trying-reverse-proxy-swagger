load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Needed for google api and also pulls in proto_library
http_archive(
    name = "com_google_protobuf",
    sha256 = "930c2c3b5ecc6c9c12615cf5ad93f1cd6e12d0aba862b572e076259970ac3a53",
    strip_prefix = "protobuf-3.21.12",
    urls = [
        "https://github.com/protocolbuffers/protobuf/archive/refs/tags/v3.21.12.tar.gz",
    ],
)
load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")
protobuf_deps()

# Needed to generate the OpenAPIv2 docs
http_archive(
    name = "io_bazel_rules_go",
    sha256 = "dd926a88a564a9246713a9c00b35315f54cbd46b31a26d5d8fb264c07045f05d",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.38.1/rules_go-v0.38.1.zip",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.38.1/rules_go-v0.38.1.zip",
    ],
)
load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")
go_rules_dependencies()
go_register_toolchains(version = "1.19.5")

http_archive(
    name = "bazel_gazelle",
    sha256 = "5982e5463f171da99e3bdaeff8c0f48283a7a5f396ec5282910b9e8a49c0dd7e",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-gazelle/releases/download/v0.25.0/bazel-gazelle-v0.25.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.25.0/bazel-gazelle-v0.25.0.tar.gz",
    ],
)
load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies", "go_repository")
gazelle_dependencies()
go_repository(
    name = "in_gopkg_yaml_v2",
    commit = "eb3733d160e74a9c7e442f435eb3bea458e1d19f",
    importpath = "gopkg.in/yaml.v2",
)

grpc_gateway_version = "2.15.0"
grpc_gateway_sha = "ffc9ee4484f22d82ae6566b7cc72b6e4f9ad63dc85eebb81f407d37f0f544c3e"
http_archive(
    name = "com_github_grpc_ecosystem_grpc_gateway",
    sha256 = grpc_gateway_sha,
    strip_prefix = "grpc-gateway-%s" % grpc_gateway_version,
    urls = ["https://github.com/grpc-ecosystem/grpc-gateway/archive/refs/tags/v%s.zip" % grpc_gateway_version],
)
load("@com_github_grpc_ecosystem_grpc_gateway//:repositories.bzl", grpc_gateway_deps = "go_repositories")
grpc_gateway_deps()
