load(
    "//reverb/cc/platform:build_rules.bzl",
    "reverb_absl_deps",
    "reverb_gen_op_wrapper_py",
    "reverb_kernel_library",
    "reverb_tf_ops_visibility",
)

package(default_visibility = reverb_tf_ops_visibility())

licenses(["notice"])

reverb_kernel_library(
    name = "client",
    srcs = ["client.cc"],
    deps = [
        "//reverb/cc:client",
    ] + reverb_absl_deps(),
)

reverb_kernel_library(
    name = "dataset",
    srcs = ["dataset.cc"],
    deps = [
        "//reverb/cc:client",
        "//reverb/cc:sampler",
        "//reverb/cc/platform:logging",
    ] + reverb_absl_deps(),
)

reverb_gen_op_wrapper_py(
    name = "gen_client_ops",
    out = "gen_client_ops.py",
    kernel_lib = ":client",
)

reverb_gen_op_wrapper_py(
    name = "gen_dataset_op",
    out = "gen_dataset_op.py",
    kernel_lib = ":dataset",
)
