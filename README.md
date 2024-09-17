# Ziggy Pydust Template

This repository contains a template for writing and packaging native Python extension modules in Zig using [Pydust](https://github.com/fulcrum-so/ziggy-pydust) framework.

This template includes:

- A Python Poetry project.
- A `src/` directory containing a Pydust Python module.
- Pytest setup for running both Python and Zig unit tests.
- GitHub Actions workflows for building and publishing the package.
- VSCode settings for recommended extensions, debugger configurations, etc.

We recommend heading to [Getting Started](https://pydust.fulcrum.so/latest/getting_started/).

# issues and fixes

- was getting the following error when running pytest:

```
/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pydantic/main.py:211: UserWarning: A custom validator is returning a value other than `self`.
Returning anything other than `self` from a top level model validator isn't supported when validating via `__init__`.
See the `model_validator` docs (https://docs.pydantic.dev/latest/concepts/validators/#model-validators) for more details.
  warnings.warn(
=============================================== test session starts ================================================
platform darwin -- Python 3.12.6, pytest-8.3.3, pluggy-1.5.0
rootdir: /Users/noor/src/zig/py-zig-test
configfile: pyproject.toml
plugins: ziggy-pydust-0.23.2
collecting ... zig test Debug native: error: error: unable to find Dynamic system library 'Python.framework/Versions/3' using strategy 'paths_first'. searched paths:
  /opt/homebrew/opt/python@3.12/Frameworks/Python.framework/Versions/3.12/lib/libPython.framework/Versions/3.tbd
  /opt/homebrew/opt/python@3.12/Frameworks/Python.framework/Versions/3.12/lib/libPython.framework/Versions/3.dylib
  /opt/homebrew/opt/python@3.12/Frameworks/Python.framework/Versions/3.12/lib/libPython.framework/Versions/3.so
  /opt/homebrew/opt/python@3.12/Frameworks/Python.framework/Versions/3.12/lib/libPython.framework/Versions/3.a
  /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/lib/libPython.framework/Versions/3.tbd
  /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/lib/libPython.framework/Versions/3.dylib
  /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/lib/libPython.framework/Versions/3.so
  /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/lib/libPython.framework/Versions/3.a

zig test Debug native: error: the following command exited with error code 1:
/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/ziglang/zig test /Users/noor/src/zig/py-zig-test/src/fib.zig -lPython.framework/Versions/3 -lc --cache-dir zig-cache --global-cache-dir /Users/noor/.cache/zig --name test --mod pydust:pyconf:/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pydust/src/pydust.zig --mod pyconf::/Users/noor/src/zig/py-zig-test/zig-cache/c/afeced1cdf7cd24fb22ed32ab5cdf00d/options.zig --mod pyconf0::/Users/noor/src/zig/py-zig-test/zig-cache/c/afeced1cdf7cd24fb22ed32ab5cdf00d/options.zig --deps pyconf=pyconf0,pydust -I /opt/homebrew/opt/python@3.12/Frameworks/Python.framework/Versions/3.12/include/python3.12 -L /opt/homebrew/opt/python@3.12/Frameworks/Python.framework/Versions/3.12/lib -rpath /opt/homebrew/opt/python@3.12/Frameworks/Python.framework/Versions/3.12/lib --listen=-
Build Summary: 1/4 steps succeeded; 1 failed (disable with --summary none)
pydust-test-build transitive failure
└─ install generated to _lib.test.bin transitive failure
   └─ zig test Debug native failure
error: the following build command failed with exit code 1:
zig-cache/o/7307e224b53ba72bfce7ed915dc8b314/build /Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/ziglang/zig /Users/noor/src/zig/py-zig-test zig-cache /Users/noor/.cache/zig pydust-test-build -Doptimize=Debug -Dpython-exe=/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/bin/python
INTERNALERROR> Traceback (most recent call last):
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/_pytest/main.py", line 283, in wrap_session
INTERNALERROR>     session.exitstatus = doit(config, session) or 0
INTERNALERROR>                          ^^^^^^^^^^^^^^^^^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/_pytest/main.py", line 336, in _main
INTERNALERROR>     config.hook.pytest_collection(session=session)
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pluggy/_hooks.py", line 513, in __call__
INTERNALERROR>     return self._hookexec(self.name, self._hookimpls.copy(), kwargs, firstresult)
INTERNALERROR>            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pluggy/_manager.py", line 120, in _hookexec
INTERNALERROR>     return self._inner_hookexec(hook_name, methods, kwargs, firstresult)
INTERNALERROR>            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pluggy/_callers.py", line 139, in _multicall
INTERNALERROR>     raise exception.with_traceback(exception.__traceback__)
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pluggy/_callers.py", line 122, in _multicall
INTERNALERROR>     teardown.throw(exception)  # type: ignore[union-attr]
INTERNALERROR>     ^^^^^^^^^^^^^^^^^^^^^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/_pytest/logging.py", line 790, in pytest_collection
INTERNALERROR>     return (yield)
INTERNALERROR>             ^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pluggy/_callers.py", line 122, in _multicall
INTERNALERROR>     teardown.throw(exception)  # type: ignore[union-attr]
INTERNALERROR>     ^^^^^^^^^^^^^^^^^^^^^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/_pytest/warnings.py", line 121, in pytest_collection
INTERNALERROR>     return (yield)
INTERNALERROR>             ^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pluggy/_callers.py", line 122, in _multicall
INTERNALERROR>     teardown.throw(exception)  # type: ignore[union-attr]
INTERNALERROR>     ^^^^^^^^^^^^^^^^^^^^^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/_pytest/config/__init__.py", line 1417, in pytest_collection
INTERNALERROR>     return (yield)
INTERNALERROR>             ^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pluggy/_callers.py", line 103, in _multicall
INTERNALERROR>     res = hook_impl.function(*args)
INTERNALERROR>           ^^^^^^^^^^^^^^^^^^^^^^^^^
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pydust/pytest_plugin.py", line 50, in pytest_collection
INTERNALERROR>     buildzig.zig_build(["pydust-test-build", f"-Doptimize={optimize}", f"-Dpython-exe={sys.executable}"])
INTERNALERROR>   File "/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/lib/python3.12/site-packages/pydust/buildzig.py", line 52, in zig_build
INTERNALERROR>     subprocess.run(cmds, check=True)
INTERNALERROR>   File "/opt/homebrew/Cellar/python@3.12/3.12.6/Frameworks/Python.framework/Versions/3.12/lib/python3.12/subprocess.py", line 571, in run
INTERNALERROR>     raise CalledProcessError(retcode, process.args,
INTERNALERROR> subprocess.CalledProcessError: Command '['/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/bin/python', '-m', 'ziglang', 'build', '--build-file', PosixPath('build.zig'), 'pydust-test-build', '-Doptimize=Debug', '-Dpython-exe=/Users/noor/.virtualenvs/ziggy-pydust-template-Dw4EsOvI-py3.12/bin/python']' returned non-zero exit status 1.

============================================== no tests ran in 0.81s
```

to fix it, manually created a link to the dynamic library

```bash
ln -s /opt/homebrew/opt/python@3.12/Frameworks/Python.framework/Versions/3.12/lib/libpython3.12.dylib /opt/homebrew/opt/python@3.12/Frameworks/Python.framework/Versions/3.12/lib/libPython.framework/Versions/3.dylib
```
