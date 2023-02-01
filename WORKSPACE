load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Needed for google api and also pulls in proto_library
http_archive(
    name = "com_google_protobuf",
    sha256 = "3bd7828aa5af4b13b99c191e8b1e884ebfa9ad371b0ce264605d347f135d2568",
    strip_prefix = "protobuf-3.19.4",
    urls = [
        "https://github.com/protocolbuffers/protobuf/archive/refs/tags/v3.19.4.tar.gz",
    ],
)
load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")
protobuf_deps()

# Needed to generate the OpenAPIv2 docs
rules_go_version = "0.25.1"
rules_go_sha = "7904dbecbaffd068651916dce77ff3437679f9d20e1a7956bff43826e7645fcc"
http_archive(
    name = "io_bazel_rules_go",
    sha256 = rules_go_sha,
    urls = [
        "https://github.com/bazelbuild/rules_go/releases/download/v{0}/rules_go-v{0}.tar.gz"
            .format(rules_go_version),
    ],
)
load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")
go_rules_dependencies()
go_register_toolchains(version = "1.16.5")

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

grpc_gateway_version = "2.5.0"
grpc_gateway_sha = "e8334c270a479f55ad9f264e798680ac536f473d7711593f6eadab3df2d1ddc3"
http_archive(
    name = "com_github_grpc_ecosystem_grpc_gateway",
    sha256 = grpc_gateway_sha,
    strip_prefix = "grpc-gateway-%s" % grpc_gateway_version,
    urls = ["https://github.com/grpc-ecosystem/grpc-gateway/archive/refs/tags/v%s.zip" % grpc_gateway_version],
)
load("@com_github_grpc_ecosystem_grpc_gateway//:repositories.bzl", grpc_gateway_deps = "go_repositories")
grpc_gateway_deps()
