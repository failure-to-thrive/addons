**Addons** is a repository of bleeding edge contributions that conform to
well-established API patterns, but implement new functionality
not available in core TensorFlow. TensorFlow natively supports
a larger number of operators, layers, metrics, losses, and optimizers.
However, in a fast moving field like ML, there are many interesting new
developments that cannot be integrated into core TensorFlow
(because they are experimental, or their significance is not yet clear).

# Scope
The tensorflow/addons repository, will contain additional functionality fitting the following criteria:

* The functionality is not otherwise available in TensorFlow
* The functionality conforms to an established API pattern in TensorFlow. For instance, it could be an additional subclass of an existing interface (new Layer, Metric, or Optimizer subclasses), or an additional Op or OpKernel implementation.
* Addons have to be compatible with TensorFlow 2.x.
* The addon conforms to the code and documentation standards defined by the group.
* The addon is useful for a large number of users (e.g., an implementation used in widely cited paper, or a utility with broad applicability)


# Developing

## Docker
**Note:** This docker container is just temporary until we can pull a
tensorflow/tensorflow:custom-op container that reflects nightly changes.
```
docker run --rm -it -v ${PWD}:/working_dir -w /working_dir seanpmorgan/addons:tf2-preview
```

## Packaging
```
./configure.sh
bazel build build_pip_pkg
bazel-bin/build_pip_pkg artifacts
```
