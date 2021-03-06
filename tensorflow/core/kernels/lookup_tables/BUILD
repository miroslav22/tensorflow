# Description:
#   OpKernels and resource templates for lookup tables.

package(
    default_visibility = [
        "//tensorflow:__subpackages__",
        "//tensorflow:internal",
    ],
)

licenses(["notice"])  # Apache 2.0

load("//tensorflow:tensorflow.bzl", "tf_kernel_library")

cc_library(
    name = "lookup_table_interface",
    hdrs = ["lookup_table_interface.h"],
    deps = [
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
        "//tensorflow/core:lib_internal",
        "@com_google_absl//absl/types:optional",
        "@com_google_absl//absl/types:span",
    ],
)

cc_library(
    name = "table_resource_utils",
    hdrs = ["table_resource_utils.h"],
    deps = [
        ":lookup_table_interface",
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
    ],
)

cc_library(
    name = "table_op_utils",
    hdrs = ["table_op_utils.h"],
    deps = [
        "//tensorflow/core:framework",
        "//tensorflow/core:framework_internal",
        "//tensorflow/core:lib",
        "//tensorflow/core:lib_internal",
        "//tensorflow/core:protos_all_cc",
        "//tensorflow/core/kernels:tensor_flag_utils",
        "//third_party/eigen3",
        "@com_google_absl//absl/base:core_headers",
        "@com_google_absl//absl/meta:type_traits",
        "@com_google_absl//absl/types:span",
    ],
)

tf_kernel_library(
    name = "fingerprint64_map_ops",
    srcs = [
        "fingerprint64_map_ops.cc",
    ],
    deps = [
        ":table_op_utils",
        ":table_resource_utils",
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
        "@com_google_absl//absl/strings",
    ],
)
