git_repository(
    name = "io_bazel_rules_python",
    remote = "https://github.com/bazelbuild/rules_python.git",
    commit = "9835856213b93594859f9c1f789d920264c8ff4f",
)

# Only needed for PIP support:
load("@io_bazel_rules_python//python:pip.bzl", "pip_repositories")

pip_repositories()

load("@io_bazel_rules_python//python:pip.bzl", "pip_import")

pip_import(
   name = "third_party",
   requirements = "//:requirements.txt",
)
load("@third_party//:requirements.bzl", "pip_install")

pip_import(
   name = "third_party_dev",
   requirements = "//:dev-requirements.txt",
)

load("@third_party_dev//:requirements.bzl", "pip_install")
pip_install()
