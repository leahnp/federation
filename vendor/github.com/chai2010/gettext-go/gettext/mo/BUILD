load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "encoder.go",
        "file.go",
        "header.go",
        "message.go",
        "util.go",
    ],
    importpath = "github.com/chai2010/gettext-go/gettext/mo",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "encoder_test.go",
        "file_test.go",
        "header_test.go",
        "util_test.go",
    ],
    importpath = "github.com/chai2010/gettext-go/gettext/mo",
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
