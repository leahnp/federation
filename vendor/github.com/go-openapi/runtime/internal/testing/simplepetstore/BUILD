load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["api.go"],
    importpath = "github.com/go-openapi/runtime/internal/testing/simplepetstore",
    visibility = ["//vendor/github.com/go-openapi/runtime:__subpackages__"],
    deps = [
        "//vendor/github.com/go-openapi/errors:go_default_library",
        "//vendor/github.com/go-openapi/loads:go_default_library",
        "//vendor/github.com/go-openapi/runtime:go_default_library",
        "//vendor/github.com/go-openapi/runtime/middleware:go_default_library",
        "//vendor/github.com/go-openapi/runtime/middleware/untyped:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["api_test.go"],
    importpath = "github.com/go-openapi/runtime/internal/testing/simplepetstore",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/go-openapi/runtime:go_default_library",
        "//vendor/github.com/stretchr/testify/assert:go_default_library",
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
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
