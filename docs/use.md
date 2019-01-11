# Use this library

This library is an internal library for the other Chaos Platform services. You
should likely not use it out of that context as it won't provide any useful
feature.

To use it in a Chaos Platform service, you would likel do this:

```python
from typing import Any, Dict, NoReturn

import attr
from chaos_relational_storage import get_storage, \
    configure_storage, release_storage


class MyServiceStorage:
    def __init__(self, config: Dict[str, Any]):
        self.driver = get_storage(config)
        configure_storage(self.driver)

    def release(self) -> NoReturn:
        """
        Release the storage resources.
        """
        release_storage(self.driver)
```

Once that class is created, you should instantiate it once and pass it around
to have access to your service's storage.

See the [settings][] page to configure the storage.

[settings]: ./settings.md
