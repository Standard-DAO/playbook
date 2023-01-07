# Python Style Guide

Follow the [Python Style Guide (PSG) as formulated in PEP-8](http://www.python.org/dev/peps/pep-0008/)

Use `pylint` to lint code. You can also use [yapf](https://github.com/google/yapf/) which is an auto-formatting tool.

## Python Versions

As a rule, all Python code should be written to support Python 3.10+. If any code fails compatibility tests with Python 3.10, it will not be accepted.

Follow the [Python Style Guide (PSG) as formulated in PEP-8](http://www.python.org/dev/peps/pep-0008/)

### Indentation

* Do not use tab for indentation
* Give 4 spaces for every indent
* Strictly enforce a 79 character line limit

Correct Indentation: :thumbsup:

```python
    Good Example  # Aligned with opening delimiter
       foo = long_function_name(var_one, var_two,
                                var_three, var_four)
       meal = (spam,
               beans)

       # Aligned with opening delimiter in a dictionary
       foo = {
           long_dictionary_key: value1 +
                                value2,
           ...
       }

       # 4-space hanging indent; nothing on first line
       foo = long_function_name(
           var_one, var_two, var_three,
           var_four)
       meal = (
           spam,
           beans)

       # 4-space hanging indent in a dictionary
       foo = {
           long_dictionary_key:
               long_dictionary_value,
           ...
       }
  ```

Incorrect indentation: :thumbsdown:

```python
    Bad Example   # Not aligned with opening delimiter
       foo = long_function_name(var_one, var_two,var_three,
       var_four)
       meal = (spam,
       beans)

       # Not aligned with opening delimiter in a dictionary
       foo = {long_dictionary_key: value1 +
                                value2,
           ...
       }

       # No space hanging indent; nothing on first line
       foo = long_function_name(
        var_one, var_two, var_three,
        var_four)
       meal = (
           spam,
           beans)

       # No space hanging indent in a dictionary
       foo = {
           long_dictionary_key:
            long_dictionary_value,
           ...
       }
  ```

### Lint

Run [pylint](https://www.pylint.org/) over your code.

Pylint can be helpful for debugging. It catches errors that are easy-to-miss errors like typos, etc.

### Naming Conventions

Use common language conventions for naming functions, classes and variables.

* Variables, functions and methods should be `lower_case_with_underscores`

```python
this_is_a_good_example
Not-A-Good-Naming-Choice
```

* Classes are `TitleCase`

```python
GoodExample
notAGoodexample
```

And other preferences:

* Use " and not ' as the quote character by default
* When writing a method, consider if it is really a method (needs self) or if it would be better as a utility function
* When writing a @classmethod, consider if it really needs the class (needs cls) or it would be better as a utility function or factory class

## Frameworks

All Python backend API work will be written using FastAPI due to its speed, ease, prevalence, and support for asynchronous functions. Write all endpoint functions synchronously unless there is a specific and obvious need for an asynchronously defined function (`async def`).

## Submitting code

* Code should be submitted via pull requests, which another person should merge.
* Use CI/CD in all repositories unless explicitly unnecessary.
  * Apps should be deployed from a continuous integration service when a successful build is made on the branch used for production.
  * Packages should be published to the respective package registry when a tag is pushed.
  * Write small, reusable libraries where possible. There are many opportunities for reuse across our different products.

## Docstrings

Use Sphinx-style or Google-style documentation conventions.

* [Sphinx-style](http://packages.python.org/an_example_pypi_project/sphinx.html#function-definitions)
* [Google Style Documentation](https://google.github.io/styleguide/pyguide.html#Comments)

### User documentation

Prefer to make really good ``README.md`` files, rather than implementing a full documentation framework.

## Testing

### tox and py.test

Use `tox` with `py.test` to test code.

* [tox overview and guide](https://tox.readthedocs.io/en/latest/)
* [py.test overview and guide](https://www.guru99.com/pytest-tutorial.html)
