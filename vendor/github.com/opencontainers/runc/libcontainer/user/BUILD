load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "lookup.go",
        "lookup_unsupported.go",
        "user.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "lookup_unix.go",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "lookup_unix.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/opencontainers/runc/libcontainer/user",
    visibility = ["//visibility:public"],
    deps = select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = ["user_test.go"],
    importpath = "github.com/opencontainers/runc/libcontainer/user",
    library = ":go_default_library",
    deps = ["//vendor/github.com/opencontainers/runc/libcontainer/utils:go_default_library"],
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
