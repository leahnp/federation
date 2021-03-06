load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "config.go",
        "config_unix.go",
        "errors.go",
        "hostconfig.go",
        "hostconfig_unix.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "config_windows.go",
            "hostconfig_windows.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/runconfig",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/docker/docker/api/types/container:go_default_library",
        "//vendor/github.com/docker/docker/api/types/network:go_default_library",
        "//vendor/github.com/docker/docker/pkg/sysinfo:go_default_library",
        "//vendor/github.com/docker/docker/volume:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "config_test.go",
        "hostconfig_test.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "hostconfig_windows_test.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/runconfig",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/docker/docker/api/types/container:go_default_library",
        "//vendor/github.com/docker/docker/api/types/network:go_default_library",
        "//vendor/github.com/docker/docker/api/types/strslice:go_default_library",
        "//vendor/github.com/docker/docker/pkg/sysinfo:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//vendor/github.com/docker/docker/runconfig/opts:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
