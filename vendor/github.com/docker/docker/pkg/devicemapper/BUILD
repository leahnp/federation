load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "log.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "devmapper.go",
            "devmapper_log.go",
            "devmapper_wrapper.go",
            "devmapper_wrapper_deferred_remove.go",
            "ioctl.go",
        ],
        "//conditions:default": [],
    }),
    cgo = True,
    clinkopts = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "-Lvendor/github.com/docker/docker/pkg/devicemapper -ldevmapper",
            "-Lvendor/github.com/docker/docker/pkg/devicemapper -ldevmapper",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/pkg/devicemapper",
    visibility = ["//visibility:public"],
    deps = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/sirupsen/logrus:go_default_library",
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "//conditions:default": [],
    }),
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
