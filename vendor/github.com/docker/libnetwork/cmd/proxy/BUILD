load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "main.go",
        "proxy.go",
        "stub_proxy.go",
        "tcp_proxy.go",
        "udp_proxy.go",
    ],
    importpath = "github.com/docker/libnetwork/cmd/proxy",
    visibility = ["//visibility:private"],
)

go_binary(
    name = "proxy",
    importpath = "github.com/docker/libnetwork/cmd/proxy",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["network_proxy_test.go"],
    importpath = "github.com/docker/libnetwork/cmd/proxy",
    library = ":go_default_library",
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
