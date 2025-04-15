workspace(name = "rules_kubebuilder")

load("@rules_kubebuilder//kubebuilder:sdk.bzl", "kubebuilder_register_sdk")

kubebuilder_register_sdk(version = "4.5.2")

## Next section is for testing in this same MP.

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_file")

http_archive(
    name = "rules_pkg",
    sha256 = "6b5969a7acd7b60c02f816773b06fcf32fbe8ba0c7919ccdc2df4f8fb923804a",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_pkg/releases/download/0.3.0/rules_pkg-0.3.0.tar.gz",
        "https://github.com/bazelbuild/rules_pkg/releases/download/0.3.0/rules_pkg-0.3.0.tar.gz",
    ],
)

load("@rules_pkg//:deps.bzl", "rules_pkg_dependencies")

rules_pkg_dependencies()

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "b4433651f57560237681cb9caa969106aba614f5b1e66fefa5834c42b8013b42",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.24.6/rules_go-v0.24.6.tar.gz",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.24.6/rules_go-v0.24.6.tar.gz",
    ],
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains()

# controller gen binaries

http_file(
    name = "controller_gen_linux_amd64",
    url = "https://github.com/kubernetes-sigs/controller-tools/releases/download/v0.17.3/controller-gen-linux-amd64",
    executable = True,
    sha256 = "21e5f3239666fc0c5e2d23c2a3a83fd655af40a969ede7a118b86832c35a829f",
)

http_file(
    name = "controller_gen_darwin_arm64",
    url = "https://github.com/kubernetes-sigs/controller-tools/releases/download/v0.17.3/controller-gen-darwin-arm64",
    executable = True,
    sha256 = "2ca28be7185d9279ed82e3355529b0543938f392cb812add3f25a62196ed7441",
)
