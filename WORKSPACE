workspace(name = "main")


load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Depend on com_google_differential_privacy and com_google_cc_differential_privacy (bazel projects)
http_archive(
    name = "com_google_differential_privacy",
    url = "https://github.com/google/differential-privacy/archive/refs/tags/v1.1.2.tar.gz",
    sha256 = "b7476712485053ed039b05bbe7481a43c8760457e6ebd7afb320d51fdf744fb5",
    strip_prefix = "differential-privacy-1.1.2",
)
http_archive(
    name = "com_google_cc_differential_privacy",
    url = "https://github.com/google/differential-privacy/archive/refs/tags/v1.1.2.tar.gz",
    sha256 = "b7476712485053ed039b05bbe7481a43c8760457e6ebd7afb320d51fdf744fb5",
    strip_prefix = "differential-privacy-1.1.2/cc",
)


# Load dependencies for the base workspace.
load("@com_google_differential_privacy//:differential_privacy_deps.bzl", "differential_privacy_deps")
differential_privacy_deps()

# Load dependencies for the cc workspace.
load("@com_google_cc_differential_privacy//:cc_differential_privacy_deps.bzl", "cc_differential_privacy_deps")
cc_differential_privacy_deps()

# Protobuf transitive dependencies.
load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")
protobuf_deps()


# Setup rules_foreign_cc (CMake integration)
http_archive(
    name = "rules_foreign_cc",
    strip_prefix = "rules_foreign_cc-8d540605805fb69e24c6bf5dc885b0403d74746a", # 0.9.0
    url = "https://github.com/bazelbuild/rules_foreign_cc/archive/8d540605805fb69e24c6bf5dc885b0403d74746a.tar.gz",
)

load("@rules_foreign_cc//foreign_cc:repositories.bzl", "rules_foreign_cc_dependencies")

rules_foreign_cc_dependencies()



# Depend on arrayfire (a non-bazel projec, built using CMake - in 3rdparty/arrayfire.BUILD)
http_archive(
    name = "arrayfire",
    build_file = "arrayfire.BUILD",
    sha256 = "2d01b35adade2433078f57e2233844679aabfdb06a41e6992a6b27c65302d3fe",
    urls = ["https://github.com/arrayfire/arrayfire/releases/download/v3.8.2/arrayfire-full-3.8.2.tar.bz2"],
    strip_prefix = "arrayfire-full-3.8.2",
)

"""
http_archive(
    name = "onednn",
    build_file = "onednn.BUILD",
    sha256 = "922b42c3ea7a7122a77c61568dc4512aa8130c264c0489283c989919d1f59a6d",
    urls = ["https://github.com/oneapi-src/oneDNN/archive/refs/tags/v2.0.tar.gz"],
    strip_prefix = "oneDNN-2.0",
)


http_archive(
    name = "gloo",
    build_file = "gloo.BUILD",
    sha256 = "c5d7fda1920dc591c041ebc0a5fad20a232a33ec7c8b02d8a9f73d4f5e77890f",
    urls = ["https://github.com/facebookincubator/gloo/archive/refs/heads/main.zip"],
    strip_prefix = "gloo-main",
)


http_archive(
    name = "flashlight",
    build_file = "flashlight.BUILD",
    sha256 = "6557f65ef2fbacc867bb6721d9134d0bc15d29e7413cbce0ae5e28d857164029",
    urls = ["https://github.com/flashlight/flashlight/archive/refs/tags/v0.3.2.tar.gz"],
    strip_prefix = "flashlight-0.3.2",
)
"""



#new_local_repository(
#    name = "arrayfire",
#    path = "/opt/arrayfire",
#    build_file = "BUILD.arrayfire",
#)



#new_local_repository(
#    name = "gloo",
#    path = "/opt/gloo",
#    build_file = "BUILD.gloo",
#)
#
#
#
#new_local_repository(
#    name = "onednn",
#    path = "/opt/onednn",
#    build_file = "BUILD.onednn",
#)
#
#
#
#new_local_repository(
#    name = "flashlight",
#    path = "/opt/flashlight",
#    build_file = "BUILD.flashlight",
#)