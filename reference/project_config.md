# Project Configuration

Project configuration defines the dependencies, prelude, backend, entry points, and other metadata to Stick project. It should be located in the root directory of the Stick project and have file `stick_config.toml` and encoded in [toml](https://github.com/toml-lang/toml).

Here's an example for a simple Stick library.

```toml
version = "0.1"
library_entry = "main"

[dependencies]
test = { type = "git", src = "some path to testing library" }
stick-native = { type = "git", src = "some path to native compiler" }

[[entries]]
name = "main"
path = "src/main"

[[entries]]
name = "test"
path = "src/test"
backend = "stick-native"
```
