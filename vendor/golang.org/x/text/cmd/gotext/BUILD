load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "extract.go",
        "main.go",
        "message.go",
    ],
    importpath = "golang.org/x/text/cmd/gotext",
    visibility = ["//visibility:private"],
    deps = [
        "//vendor/golang.org/x/text/language:go_default_library",
        "//vendor/golang.org/x/tools/go/buildutil:go_default_library",
        "//vendor/golang.org/x/tools/go/loader:go_default_library",
    ],
)

go_binary(
    name = "gotext",
    importpath = "golang.org/x/text/cmd/gotext",
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
