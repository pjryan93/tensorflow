# Description:
#   Contains the Keras preprocess layers (internal TensorFlow version).

load("//tensorflow:tensorflow.bzl", "tf_py_test")
load("//tensorflow:tensorflow.bzl", "cuda_py_test")

package(
    default_visibility = ["//visibility:public"],
    licenses = ["notice"],  # Apache 2.0
)

exports_files(["LICENSE"])

filegroup(
    name = "testdata",
    srcs = [
        "testdata/repeated_vocab.txt",
        "testdata/vocab.txt",
    ],
)

py_library(
    name = "preprocessing",
    srcs = [
        "__init__.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        ":categorical_crossing",
        ":discretization",
        ":hashing",
        ":image_preprocessing",
        ":normalization",
        ":preprocessing_stage",
        ":preprocessing_test_utils",
        ":reduction",
        ":text_vectorization",
    ],
)

py_library(
    name = "discretization",
    srcs = [
        "discretization.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:math_ops",
        "//tensorflow/python/keras/engine:base_layer",
    ],
)

py_library(
    name = "categorical_crossing",
    srcs = [
        "categorical_crossing.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:lookup_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:tensor_spec",
        "//tensorflow/python/keras/engine:base_layer",
    ],
)

py_library(
    name = "hashing",
    srcs = [
        "hashing.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:lookup_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:tensor_spec",
        "//tensorflow/python/keras/engine:base_layer",
    ],
)

py_library(
    name = "image_preprocessing",
    srcs = [
        "image_preprocessing.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:check_ops",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:image_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:stateful_random_ops",
        "//tensorflow/python:stateless_random_ops",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python/keras:backend",
        "//tensorflow/python/keras/engine:base_layer",
        "//tensorflow/python/keras/utils:tf_utils",
    ],
)

py_library(
    name = "index_lookup",
    srcs = [
        "index_lookup.py",
        "index_lookup_v1.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:lookup_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:string_ops",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python:tensor_spec",
        "//tensorflow/python:util",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/keras:backend",
        "//tensorflow/python/keras/engine:base_preprocessing_layer",
        "//tensorflow/python/ops/ragged",
    ],
)

py_library(
    name = "normalization",
    srcs = [
        "normalization.py",
        "normalization_v1.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:init_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:util",
        "//tensorflow/python/keras:backend",
        "//tensorflow/python/keras/engine:base_preprocessing_layer",
    ],
)

py_library(
    name = "text_vectorization",
    srcs = [
        "text_vectorization.py",
        "text_vectorization_v1.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        ":categorical_encoding",
        ":index_lookup",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:lookup_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:string_ops",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python:tensor_spec",
        "//tensorflow/python:util",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/keras:backend",
        "//tensorflow/python/keras/engine:base_preprocessing_layer",
        "//tensorflow/python/ops/ragged",
    ],
)

py_library(
    name = "categorical_encoding",
    srcs = [
        "categorical_encoding.py",
        "categorical_encoding_v1.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:lookup_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:string_ops",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python:tensor_spec",
        "//tensorflow/python:util",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/keras:backend",
        "//tensorflow/python/keras/engine:base_preprocessing_layer",
        "//tensorflow/python/ops/ragged",
    ],
)

py_library(
    name = "reduction",
    srcs = [
        "reduction.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:math_ops",
        "//tensorflow/python/keras:backend",
        "//tensorflow/python/keras/engine:base_layer",
    ],
)

py_library(
    name = "preprocessing_stage",
    srcs = [
        "preprocessing_stage.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:framework_ops",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/keras:engine",
        "//tensorflow/python/keras/engine:base_preprocessing_layer",
    ],
)

py_library(
    name = "preprocessing_test_utils",
    srcs = ["preprocessing_test_utils.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:client_testlib",
    ],
)

tf_py_test(
    name = "discretization_test",
    size = "small",
    srcs = ["discretization_test.py"],
    python_version = "PY3",
    deps = [
        ":discretization",
        ":preprocessing_test_utils",
        "//tensorflow/python:client_testlib",
        "@absl_py//absl/testing:parameterized",
    ],
)

cuda_py_test(
    name = "categorical_crossing_test",
    size = "medium",
    srcs = ["categorical_crossing_test.py"],
    python_version = "PY3",
    shard_count = 4,
    tags = [
        "no_windows",  # b/149031156
    ],
    deps = [
        ":categorical_crossing",
        "//tensorflow/python:client_testlib",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

cuda_py_test(
    name = "hashing_test",
    size = "medium",
    srcs = ["hashing_test.py"],
    python_version = "PY3",
    shard_count = 4,
    deps = [
        ":hashing",
        "//tensorflow/python:client_testlib",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "index_lookup_test",
    size = "medium",
    srcs = ["index_lookup_test.py"],
    data = [":testdata"],
    python_version = "PY3",
    deps = [
        ":index_lookup",
        ":preprocessing_test_utils",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python/keras",
        "//tensorflow/python/keras/utils:generic_utils",
        "//tensorflow/python/ops/ragged:ragged_string_ops",
        "@absl_py//absl/testing:parameterized",
    ],
)

cuda_py_test(
    name = "image_preprocessing_test",
    size = "medium",
    srcs = ["image_preprocessing_test.py"],
    python_version = "PY3",
    shard_count = 4,
    deps = [
        ":image_preprocessing",
        "//tensorflow/python:client_testlib",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "normalization_test",
    size = "small",
    srcs = ["normalization_test.py"],
    python_version = "PY3",
    deps = [
        ":normalization",
        ":preprocessing_test_utils",
        "//tensorflow/python:client_testlib",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "text_vectorization_test",
    size = "medium",
    srcs = ["text_vectorization_test.py"],
    python_version = "PY3",
    deps = [
        ":preprocessing_test_utils",
        ":text_vectorization",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python/keras",
        "//tensorflow/python/keras/utils:generic_utils",
        "//tensorflow/python/ops/ragged:ragged_string_ops",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "reduction_test",
    srcs = ["reduction_test.py"],
    python_version = "PY3",
    deps = [
        ":reduction",
        "//tensorflow/python:client_testlib",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "categorical_encoding_test",
    size = "medium",
    srcs = ["categorical_encoding_test.py"],
    python_version = "PY3",
    deps = [
        ":categorical_encoding",
        ":preprocessing_test_utils",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python/keras",
        "//tensorflow/python/keras/utils:generic_utils",
        "//tensorflow/python/ops/ragged:ragged_string_ops",
        "@absl_py//absl/testing:parameterized",
    ],
)

tf_py_test(
    name = "preprocessing_stage_test",
    srcs = ["preprocessing_stage_test.py"],
    python_version = "PY3",
    deps = [
        ":preprocessing_stage",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python/keras",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)
