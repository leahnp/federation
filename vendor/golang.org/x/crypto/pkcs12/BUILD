load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "bmp-string.go",
        "crypto.go",
        "errors.go",
        "mac.go",
        "pbkdf.go",
        "pkcs12.go",
        "safebags.go",
    ],
    importpath = "golang.org/x/crypto/pkcs12",
    visibility = ["//visibility:public"],
    deps = ["//vendor/golang.org/x/crypto/pkcs12/internal/rc2:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "bmp-string_test.go",
        "crypto_test.go",
        "mac_test.go",
        "pbkdf_test.go",
        "pkcs12_test.go",
    ],
    importpath = "golang.org/x/crypto/pkcs12",
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
    srcs = [
        ":package-srcs",
        "//vendor/golang.org/x/crypto/pkcs12/internal/rc2:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
