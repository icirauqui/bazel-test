# Build Arrayfire with cmake
load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

cmake(
    name = "gloo",
    cache_entries = {
        "CMAKE_BUILD_TYPE": "Release",
        "USE_MPI": "ON",
    },
    lib_source = "@gloo//:all_srcs",
    #out_static_libs = ["libaf.a", "libafcpu.a"],
)
