load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "idna.go",
        "punycode.go",
        "tables.go",
        "trie.go",
        "trieval.go",
    ],
    importpath = "golang.org/x/net/idna",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/golang.org/x/text/secure/bidirule:go_default_library",
        "//vendor/golang.org/x/text/unicode/norm:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "idna_test.go",
        "punycode_test.go",
    ],
    importpath = "golang.org/x/net/idna",
    library = ":go_default_library",
)

go_test(
    name = "go_default_xtest",
    srcs = ["example_test.go"],
    importpath = "golang.org/x/net/idna_test",
    deps = [":go_default_library"],
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
