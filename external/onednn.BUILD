# Build Arrayfire with cmake
load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

cmake(
    name = "onednn",
    cache_entries = {
        "CMAKE_BUILD_TYPE": "Release",
        "DNNL_BUILD_EXAMPLES": "OFF",
    },
    lib_source = "@onednn//:all_srcs",
    #out_static_libs = ["libdnnl.so"],
)

