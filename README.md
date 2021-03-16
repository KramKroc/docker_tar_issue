# docker_tar_issue
Reproduce issue with long names

First build the image:

```
bazel run subdir:image
```

then view the contents of the tar produced:

```
tar -tvf bazel-bin/subdir/image-layer.tar
```

You expect all files to be under `/etc/config` but any files with a FQN of longer than 100 characters stay in their original location e.g. ./long-base etc
