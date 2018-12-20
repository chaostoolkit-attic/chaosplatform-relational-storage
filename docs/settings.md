# Storage settings

The storage requires the following configuration:

```python
config = {
    "db": {
        "uri": "sqlite:///:memory:",
        "debug": False
    }
}
```

The `uri` key is the [connection string][dburi] for the underlying database
used. The `debug` flag should only be set to `True` during development as
it can be quite verbose.

[dburi]: https://docs.sqlalchemy.org/en/latest/core/engines.html#database-urls
