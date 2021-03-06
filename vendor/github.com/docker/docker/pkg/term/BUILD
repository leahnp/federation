load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "ascii.go",
        "proxy.go",
        "tc.go",
        "term.go",
        "winsize.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "termios_bsd.go",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "termios_linux.go",
        ],
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "term_windows.go",
        ],
        "//conditions:default": [],
    }),
    cgo = True,
    importpath = "github.com/docker/docker/pkg/term",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/golang.org/x/sys/unix:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "//vendor/github.com/Azure/go-ansiterm/winterm:go_default_library",
            "//vendor/github.com/docker/docker/pkg/term/windows:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = [
        "ascii_test.go",
        "proxy_test.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "term_linux_test.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/pkg/term",
    library = ":go_default_library",
    deps = ["//vendor/github.com/stretchr/testify/require:go_default_library"],
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
        "//vendor/github.com/docker/docker/pkg/term/windows:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
