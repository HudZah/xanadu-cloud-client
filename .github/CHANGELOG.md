## Release 0.3.0 (development release)

### Contributors

This release contains contributions from (in alphabetical order):

## Release 0.2.1 (current release)

### New features since last release

* Job results can now be retrieved without converting integers to `np.int64` objects.
  [(#28)](https://github.com/XanaduAI/xanadu-cloud-client/pull/28)

  ```python
  import xcc

  job = xcc.Job("<UUID>", xcc.Connection.load())

  result = job.get_result(integer_overflow_protection=False)
  ```

### Improvements

* The default HOST setting now points to `platform.xanadu.ai`.
  [(#28)](https://github.com/XanaduAI/xanadu-cloud-client/pull/28)

### Documentation

* The centralized [Xanadu Sphinx Theme](https://github.com/XanaduAI/xanadu-sphinx-theme)
  is now used to style the Sphinx documentation.
  [(#23)](https://github.com/XanaduAI/xanadu-cloud-client/pull/23)

### Contributors

This release contains contributions from (in alphabetical order):

[Mikhail Andrenkov](https://github.com/Mandrenkov).

## Release 0.2.0

### New features since last release

* The Connection class can now load a Connection from a Settings instance.
  [(#22)](https://github.com/XanaduAI/xanadu-cloud-client/pull/22)

  ```python
  import xcc

  # Initialize a Connection using an implicit Settings instance.
  connection = xcc.Connection.load()

  # Initialize a Connection using an explicit Settings instance.
  connection = xcc.Connection.load(settings=xcc.Settings())
  ```

* Following an update to the Xanadu Cloud 0.4.0 API, job lists can now be filtered by ID.
  [(#21)](https://github.com/XanaduAI/xanadu-cloud-client/pull/21)

  Using the CLI:

  ```bash
  xcc job list --ids '["<UUID 1>", "<UUID 2>", ...]'
  ```

  Using the Python API:

  ```python
  xcc.Job.list(connection, ids=["<UUID 1>", "<UUID 2>", ...])
  ```

### Improvements

* Job results are now streamed in chunks to support large payloads.
  [(#23)](https://github.com/XanaduAI/xanadu-cloud-client/pull/23)

### Bug fixes

* The license file is included in the source distribution, even when using `setuptools <56.0.0`.
  [(#20)](https://github.com/XanaduAI/xanadu-cloud-client/pull/20)

### Contributors

This release contains contributions from (in alphabetical order):

[Mikhail Andrenkov](https://github.com/Mandrenkov), [Bastian Zimmermann](https://github.com/BastianZim).

## Release 0.1.2

### Improvements

* Following an update to the Xanadu Cloud 0.4.0 API, names are no longer required to submit jobs.
  [(#16)](https://github.com/XanaduAI/xanadu-cloud-client/pull/16)

### Contributors

This release contains contributions from (in alphabetical order):

[Mikhail Andrenkov](https://github.com/Mandrenkov).

## Release 0.1.1

### New features since last release

* The Job class now has a `metadata` property which, by convention, returns
  information about job failures.
  [(#15)](https://github.com/XanaduAI/xanadu-cloud-client/pull/15)

### Improvements

* The CI workflows are now triggered when a branch is merged into `main`.
  [(#15)](https://github.com/XanaduAI/xanadu-cloud-client/pull/15)

### Bug Fixes

* On Windows, the XCC configuration file is now stored at `...\Xanadu\xanadu-cloud\.env`.
  [(#15)](https://github.com/XanaduAI/xanadu-cloud-client/pull/15)

### Documentation

* Individual modules are now listed in the *API* section of the Sphinx sidebar.
  [(#15)](https://github.com/XanaduAI/xanadu-cloud-client/pull/15)

* The Settings class docstring now includes an example walkthrough as well as
  the location of the XCC configuration file.
  [(#15)](https://github.com/XanaduAI/xanadu-cloud-client/pull/15)

### Contributors

This release contains contributions from (in alphabetical order):

[Mikhail Andrenkov](https://github.com/Mandrenkov).

## Release 0.1.0

### New features since last release

* This is the initial public release.

### Contributors

This release contains contributions from (in alphabetical order):

[Mikhail Andrenkov](https://github.com/Mandrenkov).
