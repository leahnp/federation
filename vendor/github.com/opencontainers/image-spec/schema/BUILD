load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "error.go",
        "fs.go",
        "gen.go",
        "schema.go",
        "validator.go",
    ],
    importpath = "github.com/opencontainers/image-spec/schema",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/opencontainers/go-digest:go_default_library",
        "//vendor/github.com/opencontainers/image-spec/specs-go/v1:go_default_library",
        "//vendor/github.com/pkg/errors:go_default_library",
        "//vendor/github.com/xeipuuv/gojsonschema:go_default_library",
        "//vendor/go4.org/errorutil:go_default_library",
    ],
)

go_test(
    name = "go_default_xtest",
    srcs = [
        "backwards_compatibility_test.go",
        "config_test.go",
        "descriptor_test.go",
        "imageindex_test.go",
        "manifest_test.go",
        "spec_test.go",
    ],
    importpath = "github.com/opencontainers/image-spec/schema_test",
    deps = [
        ":go_default_library",
        "//vendor/github.com/opencontainers/go-digest:go_default_library",
        "//vendor/github.com/opencontainers/image-spec/specs-go/v1:go_default_library",
        "//vendor/github.com/pkg/errors:go_default_library",
        "//vendor/github.com/russross/blackfriday:go_default_library",
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
