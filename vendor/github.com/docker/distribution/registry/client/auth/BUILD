load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "api_version.go",
        "session.go",
    ],
    importpath = "github.com/docker/distribution/registry/client/auth",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/docker/distribution/registry/client:go_default_library",
        "//vendor/github.com/docker/distribution/registry/client/auth/challenge:go_default_library",
        "//vendor/github.com/docker/distribution/registry/client/transport:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["session_test.go"],
    importpath = "github.com/docker/distribution/registry/client/auth",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/docker/distribution/registry/client/auth/challenge:go_default_library",
        "//vendor/github.com/docker/distribution/registry/client/transport:go_default_library",
        "//vendor/github.com/docker/distribution/testutil:go_default_library",
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
        "//vendor/github.com/docker/distribution/registry/client/auth/challenge:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
