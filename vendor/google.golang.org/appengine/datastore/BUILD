load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "datastore.go",
        "doc.go",
        "key.go",
        "load.go",
        "metadata.go",
        "prop.go",
        "query.go",
        "save.go",
        "transaction.go",
    ],
    importpath = "google.golang.org/appengine/datastore",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/appengine:go_default_library",
        "//vendor/google.golang.org/appengine/internal:go_default_library",
        "//vendor/google.golang.org/appengine/internal/datastore:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "datastore_test.go",
        "key_test.go",
        "load_test.go",
        "prop_test.go",
        "query_test.go",
        "time_test.go",
    ],
    importpath = "google.golang.org/appengine/datastore",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/appengine:go_default_library",
        "//vendor/google.golang.org/appengine/internal:go_default_library",
        "//vendor/google.golang.org/appengine/internal/aetesting:go_default_library",
        "//vendor/google.golang.org/appengine/internal/datastore:go_default_library",
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
