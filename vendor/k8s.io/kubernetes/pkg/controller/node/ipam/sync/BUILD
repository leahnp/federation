load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["sync.go"],
    importpath = "k8s.io/kubernetes/pkg/controller/node/ipam/sync",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/k8s.io/api/core/v1:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/controller/node/ipam/cidrset:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["sync_test.go"],
    importpath = "k8s.io/kubernetes/pkg/controller/node/ipam/sync",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/k8s.io/api/core/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/controller/node/ipam/cidrset:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/controller/node/ipam/test:go_default_library",
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
