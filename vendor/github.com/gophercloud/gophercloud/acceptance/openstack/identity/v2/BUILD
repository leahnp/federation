load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "identity.go",
        "pkg.go",
    ],
    importpath = "github.com/gophercloud/gophercloud/acceptance/openstack/identity/v2",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/gophercloud/gophercloud:go_default_library",
        "//vendor/github.com/gophercloud/gophercloud/acceptance/tools:go_default_library",
        "//vendor/github.com/gophercloud/gophercloud/openstack/identity/v2/extensions/admin/roles:go_default_library",
        "//vendor/github.com/gophercloud/gophercloud/openstack/identity/v2/tenants:go_default_library",
        "//vendor/github.com/gophercloud/gophercloud/openstack/identity/v2/users:go_default_library",
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
