load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["verify.go"],
    importpath = "github.com/influxdata/influxdb/cmd/influx_inspect/verify",
    visibility = ["//visibility:public"],
    deps = ["//vendor/github.com/influxdata/influxdb/tsdb/engine/tsm1:go_default_library"],
)

go_test(
    name = "go_default_xtest",
    srcs = ["verify_test.go"],
    importpath = "github.com/influxdata/influxdb/cmd/influx_inspect/verify_test",
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
