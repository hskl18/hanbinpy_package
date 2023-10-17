# My PyPI Package Project

A sample project to create a Python package and publish it to PyPI.

Credit to https://www.youtube.com/watch?v=Kz6IlDCyOUY

## Setting Up

To set up your Python environment for publishing your own package, you will need to install `setuptools`, `wheel`, and `twine`.

You can install these tools using pip:

```shell
pip install -r requirements.txt
```

This provides a cleaner and more straightforward way for users to interact with your package, as they can simply use `from hanbin_hello import hello` instead of navigating through deeper module structures.

```python
from hanbin_hello import hello
```

In this example, replace `'your-package-name'` with the actual name of your package. The `version` field should be set to the desired version number of your package.

Additionally, you can specify any dependencies your package requires in the `install_requires` list. For example, if your package requires NumPy version 1.11.1 or higher, you can add `'numpy>=1.11.1'` to the list.

It is also recommended to create a README.md file where you can describe your package. This file should be written in Markdown format and can provide information about the purpose of your package, how to install it, and any other relevant details.

## Build Your Package

To build your package, you will need to use the setuptools and wheel libraries. These libraries allow you to generate distribution archives that can be installed using pip. You have already installed these from the first step of this tutorial.

You can build your package by running the following command:

```bash
python setup.py sdist bdist_wheel
```

This command will generate two distribution archives: a source distribution (sdist) and a wheel distribution (bdist_wheel). These archives contain all the necessary files for installing your package.

## Local Testing

Before publishing your Python package, it's crucial to test it locally to ensure it functions correctly. Follow these steps to install and test your package using pip:

1. Open your terminal or command prompt.
2. Navigate to the directory where your package is located.
3. Run the following command to install your package locally.

```bash
pip install dist/pixegami_hello-0.1-py3-none-any.whl
```

Replace the package name with the actual name and version of your package. Once the installation is complete, you can now test your package by importing it in a Python script or interactive session and using its functionality.

```python
# In a different file...
from pixegami_hello import hello

hello() # Hello from Pixegami!
```

By testing your package locally, you can identify and fix any issues before publishing it to PyPI.

## Add a CLI Command

If you want to turn this package into a command line interface (or CLI application), you can also do that.

In the `setup.py` file, you can specify entry points for your package, which lets you a command name to any function inside your package. And running that command will run that function.

```python
setup(
    ...
    entry_points={
        "console_scripts": [
            "pixegami-hello = pixegami_hello:hello",
        ],
    },
)
```

## Publish to PyPI

To publish your Python package to PyPI, you can use the twine tool.

```bash
twine upload dist/*
```

You will be prompted for your PyPI credentials. Once uploaded, anyone can install your package using.

```bash
pip install pixegami-hello
```

## Useful Links

- [Python Packaging User Guide](https://packaging.python.org/)
- [setuptools documentation](https://setuptools.readthedocs.io/)
- [wheel documentation](https://wheel.readthedocs.io/)
- [twine documentation](https://twine.readthedocs.io/)
- [PyPI](https://pypi.org/)
