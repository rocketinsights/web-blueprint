# [Nicolas Carbone's](https://github.com/nicolascarbone) Soapbox of Python Practices

This soapbox contains some basic stuff for different Python projects.

## Environment setup

### Virtual Envs

A virtual environment is a Python environment such that the Python interpreter, libraries and scripts installed into it are isolated from those installed in other virtual environments, and (by default) any libraries installed in a “system” Python, i.e., one which is installed as part of your operating system.

This will help you to install project dependencies in an isolate environment without installing anything at system level.

You can easily create a new virtual environment running:

`python3 -m venv your-project`

See [Python docs](https://docs.python.org/3/tutorial/venv.html) for a complete reference.

#### Managing packages

Once the virtual environment is running, you can install packages using [pip](https://docs.python.org/3/installing/index.html#installing-index)

##### Other tools

There are some tools to make this process easier, like [pipenv](https://pypi.org/project/pipenv/)
which allows you to create a virtual env and also install packages and
[Poetry](https://python-poetry.org) to easily manage dependencies.

## Coding Style

Python has defined a coding style guide called PEP8, lease refer to [PEP8](https://www.python.org/dev/peps/pep-0008/) for a complete reference.

You should always stick to this guide, it is in most of the python projects.

Most important styles are:
- Use spaces instead of tabs.
- Use underscode for function, methods, variables and file names:
    - Examples: get_user, client_name, set_date, etc
- Use camel case for class names: MyClass, MyService, etc
- Use capital letter at module level for constants.
- Use `self` as first argument to instance methods.
- Use `cls` as first argument to class methods.

### Linting

There are many linters in Python, choose the one you like the most and stick to it.
Some of them are
- [Pylint](https://www.pylint.org)
- [Flake8](https://flake8.pycqa.org/en/latest/)
- [Pylama](https://readthedocs.org/projects/pylama/)
etc

The whole team should use the same linter for sake of consistency.

You can also use git hooks to make sure you don't push any code that does not pass a linter analysis.

### Formatting

There are many formatters in python, check [Here](https://github.com/life4/awesome-python-code-formatters) for a detailed list.

Choose the one you like the most but please use at least one.

Again, the whole team should use the same formatter for consistency.

Formatters can run in a git hook or as an IDE plugin.

### Import statements

Keep imports sorted, the following is a very common convention

```
<python standard lib imporst>

<third party imports>

<app packages>

<tests> (if it is a test suite)
```

You can always use plugins like [isort](https://pypi.org/project/isort/) to do this when you save a file or in a git hook.

### Private Class Properties

Python does not have access modifiers so use a leading `_` for private methods.

Avoid using leading `__` because that will trigger a process called `name mangling`, it will just put the classname as attribute preffix.

## Coding Practices

As general rule, your code should have high cohesion and low coupling, this will make it easier to maintain, scale, etc.

Some things to keep in mind:
- Dependency Injection: This will decouple your services from other ones and it will make them easier to test and maintain.

    See [Example](https://gist.github.com/nicolascarbone/48a837ecab8b8d84250deaf012b36307)
    and this [post](https://levelup.gitconnected.com/dependency-injection-in-python-3-with-testing-55b64ca60ae1) for a
    more complete example.

- Repository pattern: all CRUD operations should go here so your services won't get tied to the db layer.

    See [Example](https://gist.github.com/nicolascarbone/4838a48852b1ae03b8095dc4cfa8d008)

    Then you can use this class to access to your data from your services.

- Single responsability: Avoid adding more than one responsability to each function/method. This will make you code simpler and easier to test.
- Unit of work: this is a useful pattern which collaborates with the repository pattern to coordinate the writing out of changes. It is an abstraction for atomic operation, so the API does not communicate with all the other layers.

    See [Chapter](https://www.cosmicpython.com/book/chapter_06_uow.html) of the amazing book by Harry Percival.

### Accessing to the database.

Whenever possible use an ORM to access to the database, this can help to make your app compatible with different db engines like:
- Postgres
- Mssql
- Sqlite

A common option is [SqlAlchemy](https://www.sqlalchemy.org) but there are others like [Peewee](http://docs.peewee-orm.com/en/latest/).

When using an ORM avoid writing raw sql unless is strickly necessary, this will tie your code to 
an specific db engine.

### Testing

Python has unittest as part of the standard lib, however, there are more flexible tools and frameworks
like [Pytest](https://docs.pytest.org/en/stable/index.html), which has some really useful features that makes
tests more scalable and it is widely accepted by the python community.

Considerations:
- Each function or method should have its own test
- Keep an eye on responsabilites and make sure you function/method does only one thing,
    this will allow you to write smaller and more reliable tests.
- Mock any third-party lib.
    - You can use mock and patch from unittest for this purpose.
- Use dependency injection: this will allow you to use mocks to easily test services without patching a lot of different classes.

    ```
    cache = mock.Mock()
    my_service(cache=cache)
    cache.get.assert_called_with(key)
    ```
