package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_binary",
    "go_library",
)

go_binary(
    name = "cmd",
    embed = [":go_default_library"],
    tags = ["automanaged"],
)

go_library(
    name = "go_default_library",
    srcs = ["main.go"],
    data = ["account-service-example.toml"],
    importpath = "go-common/app/service/main/account/cmd",
    tags = ["automanaged"],
    deps = [
        "//app/service/main/account/conf:go_default_library",
        "//app/service/main/account/rpc/server:go_default_library",
        "//app/service/main/account/server/grpc:go_default_library",
        "//app/service/main/account/server/http:go_default_library",
        "//app/service/main/account/service:go_default_library",
        "//library/log:go_default_library",
        "//library/net/rpc/warden:go_default_library",
        "//library/net/rpc/warden/resolver/livezk:go_default_library",
        "//library/net/trace:go_default_library",
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
