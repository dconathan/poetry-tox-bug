This is a minimal package to reproduce a bug I am seeing with poetry, tox and overlapping extras.

To reproduce:

(tox.ini)

```shell
python3 -m venv .venv
./.venv/bin/python -m pip install tox
./.venv/bin/tox
```

Will raise an error:

```python
pip._vendor.packaging.markers.InvalidMarker: Invalid marker: 'or extra == "extras2"', parse error at 'or extra'
```