load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
        name = "com_google_protobuf",
        sha256 = "c6003e1d2e7fefa78a3039f19f383b4f3a61e81be8c19356f85b6461998ad3db",
        strip_prefix = "protobuf-3.17.3",
        urls = ["https://github.com/protocolbuffers/protobuf/archive/v3.17.3.tar.gz"],
    )


load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")
protobuf_deps()