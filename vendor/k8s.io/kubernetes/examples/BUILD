package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

filegroup(
    name = "config",
    srcs = glob([
        "**/*.yaml",
        "**/*.yml",
        "**/*.json",
    ]) + [
        "pod",
    ],
)

go_library(
    name = "go_default_library",
    srcs = ["doc.go"],
    importpath = "k8s.io/kubernetes/examples",
)

go_test(
    name = "go_default_xtest",
    srcs = ["examples_test.go"],
    importpath = "k8s.io/kubernetes/examples_test",
    tags = ["manual"],  # this test is broken and examples in-tree is deprecated
    deps = [
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/types:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/validation/field:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/yaml:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/api:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/api/testapi:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/api/validation:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/apis/apps:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/apis/apps/validation:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/apis/batch:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/apis/extensions:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/apis/extensions/validation:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/capabilities:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/registry/batch/job:go_default_library",
        "//vendor/k8s.io/kubernetes/plugin/pkg/scheduler/api:go_default_library",
        "//vendor/k8s.io/kubernetes/plugin/pkg/scheduler/api/latest:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//vendor/k8s.io/kubernetes/examples/explorer:all-srcs",
        "//vendor/k8s.io/kubernetes/examples/guestbook-go:all-srcs",
        "//vendor/k8s.io/kubernetes/examples/https-nginx:all-srcs",
        "//vendor/k8s.io/kubernetes/examples/sharing-clusters:all-srcs",
    ],
    tags = ["automanaged"],
)
