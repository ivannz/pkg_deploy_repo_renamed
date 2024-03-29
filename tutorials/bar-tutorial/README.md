# Installing git subfolder via pip

This is based on the recently merged [pip feature](https://pip.readthedocs.io/en/stable/reference/pip_install/#vcs-support).

## Packaging: how do?

Here is a lengthy but complete [documentation](https://packaging.python.org/guides/distributing-packages-using-setuptools/#setup-py) on how packaging is done. It links to a [PyPA sample project](https://github.com/pypa/sampleproject), that can be used as a template.

# Installing foo-tutorial

Here is how you can install the dependency of the foo-tutorial
```bash
pip install --upgrade \
git+https://github.com/ivannz/test-tutorial-repo.git#\
subdirectory=tutorials/foo-tutorial
```


# Installing bar-tutorial

Installing `bar` is trivial:
```bash
pip install --upgrade -q git+file:///Users/user/Github/test_repo#subdirectory=tutorials/bar-tutorial
```

Accessing package data can be done like this:
```python
from pkg_resources import resource_stream

# data URI is relative to the package name. This is specified in setup.py
with resource_stream("bar", "data/dataset.txt") as fin:
    pass
```
