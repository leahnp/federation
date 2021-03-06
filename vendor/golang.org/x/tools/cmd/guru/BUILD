load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "callees.go",
        "callers.go",
        "callstack.go",
        "definition.go",
        "describe.go",
        "freevars.go",
        "guru.go",
        "implements.go",
        "isAlias18.go",
        "isAlias19.go",
        "main.go",
        "peers.go",
        "pointsto.go",
        "pos.go",
        "referrers.go",
        "what.go",
        "whicherrs.go",
    ],
    importpath = "golang.org/x/tools/cmd/guru",
    visibility = ["//visibility:private"],
    deps = [
        "//vendor/golang.org/x/tools/cmd/guru/serial:go_default_library",
        "//vendor/golang.org/x/tools/go/ast/astutil:go_default_library",
        "//vendor/golang.org/x/tools/go/buildutil:go_default_library",
        "//vendor/golang.org/x/tools/go/callgraph:go_default_library",
        "//vendor/golang.org/x/tools/go/callgraph/static:go_default_library",
        "//vendor/golang.org/x/tools/go/loader:go_default_library",
        "//vendor/golang.org/x/tools/go/pointer:go_default_library",
        "//vendor/golang.org/x/tools/go/ssa:go_default_library",
        "//vendor/golang.org/x/tools/go/ssa/ssautil:go_default_library",
        "//vendor/golang.org/x/tools/go/types/typeutil:go_default_library",
        "//vendor/golang.org/x/tools/refactor/importgraph:go_default_library",
    ],
)

go_binary(
    name = "guru",
    importpath = "golang.org/x/tools/cmd/guru",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["unit_test.go"],
    importpath = "golang.org/x/tools/cmd/guru",
    library = ":go_default_library",
)

go_test(
    name = "go_default_xtest",
    srcs = ["guru_test.go"],
    importpath = "golang.org/x/tools/cmd/guru_test",
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
    srcs = [
        ":package-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/serial:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/alias:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/calls:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/calls-json:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/definition-json:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/describe:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/describe-json:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/freevars:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/implements:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/implements-json:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/implements-methods:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/implements-methods-json:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/imports:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/lib:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/main:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/peers:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/peers-json:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/pointsto:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/pointsto-json:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/referrers:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/referrers-json:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/reflection:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/softerrs:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/what:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/what-json:all-srcs",
        "//vendor/golang.org/x/tools/cmd/guru/testdata/src/whicherrs:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
