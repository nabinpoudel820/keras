# Description:
#   Contains the Keras Utilities (internal TensorFlow version).

load("@org_keras//keras:keras.bzl", "tf_py_test")

package(
    # TODO(scottzhu): Remove non-keras deps from TF.
    default_visibility = [
        "//keras:friends",
        "//third_party/tensorflow/python/feature_column:__pkg__",
        "//third_party/tensorflow/tools/pip_package:__pkg__",
    ],
    licenses = ["notice"],
)

py_library(
    name = "utils",
    srcs = [
        "__init__.py",
    ],
    srcs_version = "PY3",
    deps = [
        ":all_utils",
    ],
)

py_library(
    name = "all_utils",
    srcs = [
        "all_utils.py",
    ],
    srcs_version = "PY3",
    deps = [
        ":control_flow_util",
        ":engine_utils",
        ":generic_utils",
        ":keras_doctest_lib",
        ":layer_utils",
        ":np_utils",
        ":traceback_utils",
        ":vis_utils",
    ],
)

py_library(
    name = "control_flow_util",
    srcs = ["control_flow_util.py"],
    srcs_version = "PY3",
    deps = [],
)

py_library(
    name = "kpl_test_utils",
    srcs = ["kpl_test_utils.py"],
    srcs_version = "PY3",
    deps = [
        "//keras",
        "//keras/layers/preprocessing:string_lookup",
    ],
)

py_library(
    name = "data_utils",
    srcs = ["data_utils.py"],
    srcs_version = "PY3",
    deps = [
        ":generic_utils",
        ":io_utils",
        ":tf_inspect",
    ],
)

py_library(
    name = "engine_utils",
    srcs = [
        "conv_utils.py",
        "losses_utils.py",
    ],
    srcs_version = "PY3",
    deps = [
        ":data_utils",
        ":io_utils",
        "//keras:backend",
    ],
)

py_library(
    name = "io_utils",
    srcs = ["io_utils.py"],
    srcs_version = "PY3",
    deps = [
        ":keras_logging",
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "keras_logging",
    srcs = ["keras_logging.py"],
    srcs_version = "PY3",
)

py_library(
    name = "tf_utils",
    srcs = ["tf_utils.py"],
    srcs_version = "PY3",
    deps = [
        ":object_identity",
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "traceback_utils",
    srcs = ["traceback_utils.py"],
    srcs_version = "PY3",
    deps = [
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "generic_utils",
    srcs = [
        "generic_utils.py",
    ],
    srcs_version = "PY3",
    deps = [
        ":io_utils",
        ":tf_contextlib",
        ":tf_inspect",
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "mode_keys",
    srcs = [
        "mode_keys.py",
    ],
    srcs_version = "PY3",
    deps = [
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "layer_utils",
    srcs = [
        "kernelized_utils.py",
        "layer_utils.py",
    ],
    srcs_version = "PY3",
    deps = [
        ":engine_utils",
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
        "//keras:backend",
    ],
)

py_library(
    name = "metrics_utils",
    srcs = [
        "metrics_utils.py",
    ],
    srcs_version = "PY3",
    deps = [
        ":generic_utils",
        ":tf_utils",
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "version_utils",
    srcs = [
        "version_utils.py",
    ],
    srcs_version = "PY3",
    deps = [
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "np_utils",
    srcs = [
        "np_utils.py",
    ],
    srcs_version = "PY3",
    deps = [
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "object_identity",
    srcs = ["object_identity.py"],
    srcs_version = "PY3",
    deps = [],
)

py_library(
    name = "tf_contextlib",
    srcs = ["tf_contextlib.py"],
    srcs_version = "PY3",
    deps = [
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "tf_inspect",
    srcs = ["tf_inspect.py"],
    srcs_version = "PY3",
    deps = [
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "vis_utils",
    srcs = [
        "vis_utils.py",
    ],
    srcs_version = "PY3",
    deps = [
        "//:expect_tensorflow_installed",
    ],
)

py_library(
    name = "dataset_creator",
    srcs = [
        "dataset_creator.py",
    ],
    srcs_version = "PY3",
    deps = [
        "//:expect_tensorflow_installed",
    ],
)

tf_py_test(
    name = "dataset_creator_test",
    srcs = ["dataset_creator_test.py"],
    python_version = "PY3",
    deps = [
        ":dataset_creator",
        "//:expect_portpicker_installed",
        "//:expect_tensorflow_installed",
        "//keras:combinations",
        "//keras/distribute:multi_worker_testing_utils",
        "//keras/engine",
        "//keras/layers/core",
    ],
)

tf_py_test(
    name = "data_utils_test",
    size = "medium",
    srcs = ["data_utils_test.py"],
    python_version = "PY3",
    shard_count = 6,
    tags = [
        "noasan",  # times out
        "notsan",
        "optonly",  # times out
    ],
    deps = [
        "//:expect_absl_installed",
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
        "//keras",
    ],
)

tf_py_test(
    name = "generic_utils_test",
    size = "small",
    srcs = ["generic_utils_test.py"],
    python_version = "PY3",
    deps = [
        ":generic_utils",
        "//:expect_absl_installed",
        "//:expect_tensorflow_installed",
        "//keras",
    ],
)

tf_py_test(
    name = "version_utils_test",
    size = "small",
    srcs = ["version_utils_test.py"],
    python_version = "PY3",
    deps = [
        ":version_utils",
        "//:expect_absl_installed",
        "//:expect_tensorflow_installed",
        "//keras",
    ],
)

tf_py_test(
    name = "tf_utils_test",
    size = "small",
    srcs = ["tf_utils_test.py"],
    python_version = "PY3",
    deps = [
        ":tf_utils",
        "//:expect_tensorflow_installed",
        "//keras",
        "//keras:combinations",
    ],
)

tf_py_test(
    name = "composite_tensor_support_test",
    size = "medium",
    srcs = ["composite_tensor_support_test.py"],
    python_version = "PY3",
    shard_count = 8,
    deps = [
        "//:expect_absl_installed",
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
        "//keras",
        "//keras:engine",
        "//keras/layers",
    ],
)

tf_py_test(
    name = "io_utils_test",
    size = "small",
    srcs = ["io_utils_test.py"],
    python_version = "PY3",
    tags = [
        "no_windows",  # TODO: needs investigation on Windows
        "notsan",
    ],
    deps = [
        ":io_utils",
        ":keras_logging",
        "//:expect_absl_installed",
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
        "//keras",
    ],
)

tf_py_test(
    name = "layer_utils_test",
    size = "small",
    srcs = ["layer_utils_test.py"],
    python_version = "PY3",
    deps = [
        ":layer_utils",
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
        "//keras",
    ],
)

tf_py_test(
    name = "np_utils_test",
    size = "small",
    srcs = ["np_utils_test.py"],
    python_version = "PY3",
    deps = [
        "//:expect_absl_installed",
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
        "//keras",
    ],
)

tf_py_test(
    name = "kernelized_utils_test",
    size = "small",
    srcs = ["kernelized_utils_test.py"],
    python_version = "PY3",
    deps = [
        ":layer_utils",
        "//:expect_absl_installed",
        "//:expect_tensorflow_installed",
    ],
)

tf_py_test(
    name = "vis_utils_test",
    size = "small",
    srcs = ["vis_utils_test.py"],
    python_version = "PY3",
    shard_count = 4,
    deps = [
        "//:expect_absl_installed",
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
        "//keras",
    ],
)

tf_py_test(
    name = "conv_utils_test",
    size = "small",
    srcs = ["conv_utils_test.py"],
    python_version = "PY3",
    deps = [
        "//:expect_absl_installed",
        "//:expect_numpy_installed",
        "//:expect_tensorflow_installed",
        "//keras",
    ],
)

tf_py_test(
    name = "metrics_utils_test",
    size = "small",
    srcs = ["metrics_utils_test.py"],
    python_version = "PY3",
    deps = [
        "//:expect_absl_installed",
        "//:expect_tensorflow_installed",
        "//keras",
        "//keras:combinations",
    ],
)

tf_py_test(
    name = "losses_utils_test",
    size = "small",
    srcs = ["losses_utils_test.py"],
    python_version = "PY3",
    deps = [
        "//:expect_tensorflow_installed",
        "//keras",
        "//keras:combinations",
    ],
)

tf_py_test(
    name = "traceback_utils_test",
    size = "small",
    srcs = ["traceback_utils_test.py"],
    python_version = "PY3",
    deps = [
        "//:expect_tensorflow_installed",
        "//keras",
    ],
)

# TODO(mattdangerw): For now, keras will maintain it's own doc checker.
# If tensorflow exposes one, we could consider depending on that directly.
py_library(
    name = "keras_doctest_lib",
    srcs = ["keras_doctest_lib.py"],
    srcs_version = "PY3",
    deps = [
        "//:expect_numpy_installed",
    ],
)

py_test(
    name = "keras_doctest_lib_test",
    srcs = ["keras_doctest_lib_test.py"],
    python_version = "PY3",
    tags = [
        "noasan",
        "nomsan",
        "notsan",
    ],
    deps = [
        ":keras_doctest_lib",
        "//:expect_absl_installed",
        "//:expect_tensorflow_installed",
    ],
)
