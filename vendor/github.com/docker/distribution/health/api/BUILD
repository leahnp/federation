load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["api.go"],
    importpath = "github.com/docker/distribution/health/api",
    visibility = ["//visibility:public"],
    deps = ["//vendor/github.com/docker/distribution/health:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = ["api_test.go"],
    importpath = "github.com/docker/distribution/health/api",
    library = ":go_default_library",
    deps = ["//vendor/github.com/docker/distribution/health:go_default_library"],
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
