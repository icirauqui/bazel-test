# Build Arrayfire with cmake
load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

cmake(
    name = "flashlight",
    cache_entries = {
        "CMAKE_BUILD_TYPE": "Release",
        "FL_BUILD_ALL_LIBS": "ON",
        "FL_BACKEND": "CPU",
    },
    deps = [
        "#onednn",
        "#gloo",
        "@arrayfire",
    ],
    lib_source = "@flashlight//:all_srcs",
    #out_static_libs = ["libaf.a", "libafcpu.a"],
)

