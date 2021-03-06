load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "client.go",
        "clientconfig.go",
        "defaults.go",
        "dns.go",
        "dnssec.go",
        "dnssec_keygen.go",
        "dnssec_keyscan.go",
        "dnssec_privkey.go",
        "doc.go",
        "edns.go",
        "format.go",
        "generate.go",
        "labels.go",
        "msg.go",
        "msg_helpers.go",
        "nsecx.go",
        "privaterr.go",
        "rawmsg.go",
        "reverse.go",
        "sanitize.go",
        "scan.go",
        "scan_rr.go",
        "scanner.go",
        "server.go",
        "sig0.go",
        "singleinflight.go",
        "tlsa.go",
        "tsig.go",
        "types.go",
        "udp.go",
        "udp_other.go",
        "update.go",
        "xfr.go",
        "zmsg.go",
        "ztypes.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "udp_linux.go",
        ],
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "udp_windows.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/miekg/dns",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "client_test.go",
        "clientconfig_test.go",
        "dns_bench_test.go",
        "dns_test.go",
        "dnssec_test.go",
        "dyn_test.go",
        "edns_test.go",
        "fuzz_test.go",
        "issue_test.go",
        "labels_test.go",
        "nsecx_test.go",
        "parse_test.go",
        "remote_test.go",
        "sanitize_test.go",
        "server_test.go",
        "sig0_test.go",
        "tsig_test.go",
        "types_test.go",
        "update_test.go",
    ],
    importpath = "github.com/miekg/dns",
    library = ":go_default_library",
)

go_test(
    name = "go_default_xtest",
    srcs = [
        "example_test.go",
        "privaterr_test.go",
    ],
    importpath = "github.com/miekg/dns_test",
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
        "//vendor/github.com/miekg/dns/dnsutil:all-srcs",
        "//vendor/github.com/miekg/dns/idn:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
