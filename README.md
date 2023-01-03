This is a minimal package to reproduce a bug I am seeing with poetry, tox and overlapping extras.

To reproduce:

```shell
python3 -m venv .venv
./.venv/bin/python -m pip install "tox<4.1.2"
./.venv/bin/tox
```

Will raise an error:

```python
pip._vendor.packaging.markers.InvalidMarker: Invalid marker: 'or extra == "extras2"', parse error at 'or extra'
```

### Update

This bug was fixed in [tox 4.1.2](https://github.com/tox-dev/tox/releases/tag/4.1.2) via [#2792](https://github.com/tox-dev/tox/pull/2792)