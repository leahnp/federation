load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "compress-memcopy.go",
        "compress-nomemcopy.go",
        "debug.go",
        "nocompress-memcopy.go",
        "nocompress-nomemcopy.go",
    ],
    importpath = "github.com/jteeuwen/go-bindata/testdata/out",
    visibility = ["//visibility:private"],
)

go_binary(
    name = "out",
    importpath = "github.com/jteeuwen/go-bindata/testdata/out",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
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
