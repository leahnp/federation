load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["cli.go"],
    importpath = "github.com/influxdata/influxdb/cmd/influx/cli",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/influxdata/influxdb/client:go_default_library",
        "//vendor/github.com/influxdata/influxdb/importer/v8:go_default_library",
        "//vendor/github.com/influxdata/influxdb/models:go_default_library",
        "//vendor/github.com/peterh/liner:go_default_library",
        "//vendor/golang.org/x/crypto/ssh/terminal:go_default_library",
    ],
)

go_test(
    name = "go_default_xtest",
    srcs = ["cli_test.go"],
    importpath = "github.com/influxdata/influxdb/cmd/influx/cli_test",
    deps = [
        ":go_default_library",
        "//vendor/github.com/influxdata/influxdb/client:go_default_library",
        "//vendor/github.com/influxdata/influxdb/influxql:go_default_library",
        "//vendor/github.com/peterh/liner:go_default_library",
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
