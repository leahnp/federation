load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "auth.go",
        "balancer.go",
        "client.go",
        "cluster.go",
        "compact_op.go",
        "compare.go",
        "config.go",
        "doc.go",
        "kv.go",
        "lease.go",
        "logger.go",
        "maintenance.go",
        "op.go",
        "retry.go",
        "sort.go",
        "txn.go",
        "watch.go",
    ],
    importpath = "github.com/coreos/etcd/clientv3",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/coreos/etcd/auth/authpb:go_default_library",
        "//vendor/github.com/coreos/etcd/etcdserver/api/v3rpc/rpctypes:go_default_library",
        "//vendor/github.com/coreos/etcd/etcdserver/etcdserverpb:go_default_library",
        "//vendor/github.com/coreos/etcd/mvcc/mvccpb:go_default_library",
        "//vendor/github.com/coreos/etcd/pkg/tlsutil:go_default_library",
        "//vendor/github.com/ghodss/yaml:go_default_library",
        "//vendor/github.com/grpc-ecosystem/go-grpc-prometheus:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/grpc:go_default_library",
        "//vendor/google.golang.org/grpc/codes:go_default_library",
        "//vendor/google.golang.org/grpc/credentials:go_default_library",
        "//vendor/google.golang.org/grpc/grpclog:go_default_library",
        "//vendor/google.golang.org/grpc/metadata:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "balancer_test.go",
        "client_test.go",
        "compact_op_test.go",
        "config_test.go",
        "op_test.go",
        "txn_test.go",
        "watch_test.go",
    ],
    importpath = "github.com/coreos/etcd/clientv3",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/coreos/etcd/etcdserver/api/v3rpc/rpctypes:go_default_library",
        "//vendor/github.com/coreos/etcd/etcdserver/etcdserverpb:go_default_library",
        "//vendor/github.com/coreos/etcd/mvcc/mvccpb:go_default_library",
        "//vendor/github.com/coreos/etcd/pkg/testutil:go_default_library",
        "//vendor/github.com/ghodss/yaml:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/grpc:go_default_library",
    ],
)

go_test(
    name = "go_default_xtest",
    srcs = [
        "example_auth_test.go",
        "example_cluster_test.go",
        "example_kv_test.go",
        "example_lease_test.go",
        "example_maintenence_test.go",
        "example_metrics_test.go",
        "example_test.go",
        "example_watch_test.go",
        "main_test.go",
    ],
    importpath = "github.com/coreos/etcd/clientv3_test",
    deps = [
        ":go_default_library",
        "//vendor/github.com/coreos/etcd/auth:go_default_library",
        "//vendor/github.com/coreos/etcd/etcdserver/api/v3rpc/rpctypes:go_default_library",
        "//vendor/github.com/coreos/etcd/integration:go_default_library",
        "//vendor/github.com/coreos/etcd/pkg/testutil:go_default_library",
        "//vendor/github.com/coreos/etcd/pkg/transport:go_default_library",
        "//vendor/github.com/coreos/pkg/capnslog:go_default_library",
        "//vendor/github.com/prometheus/client_golang/prometheus:go_default_library",
        "//vendor/golang.org/x/crypto/bcrypt:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
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
        "//vendor/github.com/coreos/etcd/clientv3/concurrency:all-srcs",
        "//vendor/github.com/coreos/etcd/clientv3/integration:all-srcs",
        "//vendor/github.com/coreos/etcd/clientv3/mirror:all-srcs",
        "//vendor/github.com/coreos/etcd/clientv3/naming:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
