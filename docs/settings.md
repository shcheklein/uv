## Global
#### [`index-url`](#index-url) {: #index-url }

The URL of the Python package index (by default: <https://pypi.org/simple>).

Accepts either a repository compliant with PEP 503 (the simple repository API), or a local
directory laid out in the same format.

The index provided by this setting is given lower priority than any indexes specified via
[`extra_index_url`](#extra-index-url).

**Default value**: `https://pypi.org/simple`

**Type**: `str`

**Example usage**:

=== "pyproject.toml"

    ```toml
    [tool.uv]
    index-url = "https://pypi.org/simple"
    ```
=== "uv.toml"

    ```toml
    
    index-url = "https://pypi.org/simple"
    ```

---

#### [`managed`](#managed) {: #managed }

Whether the project is managed by `uv`. If `false`, `uv` will ignore the project when
`uv run` is invoked.

**Default value**: `true`

**Type**: `bool`

**Example usage**:

=== "pyproject.toml"

    ```toml
    [tool.uv]
    managed = false
    ```
=== "uv.toml"

    ```toml
    
    managed = false
    ```

---

## `pip`

Settings that are specific to the `uv pip` command-line interface.

These values will be ignored when running commands outside the `uv pip` namespace (e.g.,
`uv lock`, `uvx`).

#### [`no-header`](#pip_no-header) {: #pip_no-header }
<span id="no-header"></span>

Exclude the comment header at the top of output file generated by `uv pip compile`.

**Default value**: `false`

**Type**: `bool`

**Example usage**:

=== "pyproject.toml"

    ```toml
    [tool.uv.pip]
    no-header = true
    ```
=== "uv.toml"

    ```toml
    [pip]
    no-header = true
    ```

---

## `workspace`

#### [`exclude`](#workspace_exclude) {: #workspace_exclude }
<span id="exclude"></span>

Packages to exclude as workspace members. If a package matches both `members` and
`exclude`, it will be excluded.

Supports both globs and explicit paths.

For more information on the glob syntax, refer to the [`glob` documentation](https://docs.rs/glob/latest/glob/struct.Pattern.html).

**Default value**: `[]`

**Type**: `list[str]`

**Example usage**:

=== "pyproject.toml"

    ```toml
    [tool.uv.workspace]
    exclude = ["member1", "path/to/member2", "libs/*"]
    ```
=== "uv.toml"

    ```toml
    [workspace]
    exclude = ["member1", "path/to/member2", "libs/*"]
    ```

---

#### [`members`](#workspace_members) {: #workspace_members }
<span id="members"></span>

Packages to include as workspace members.

Supports both globs and explicit paths.

For more information on the glob syntax, refer to the [`glob` documentation](https://docs.rs/glob/latest/glob/struct.Pattern.html).

**Default value**: `[]`

**Type**: `list[str]`

**Example usage**:

=== "pyproject.toml"

    ```toml
    [tool.uv.workspace]
    members = ["member1", "path/to/member2", "libs/*"]
    ```
=== "uv.toml"

    ```toml
    [workspace]
    members = ["member1", "path/to/member2", "libs/*"]
    ```

---

