load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "container_hints.go",
        "fsHandler.go",
        "helpers.go",
        "inotify_watcher.go",
    ],
    importpath = "github.com/google/cadvisor/container/common",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/github.com/google/cadvisor/container:go_default_library",
        "//vendor/github.com/google/cadvisor/fs:go_default_library",
        "//vendor/github.com/google/cadvisor/info/v1:go_default_library",
        "//vendor/github.com/google/cadvisor/utils:go_default_library",
        "//vendor/golang.org/x/exp/inotify:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["container_hints_test.go"],
    importpath = "github.com/google/cadvisor/container/common",
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
