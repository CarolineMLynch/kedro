However, if you just want to use this Hook to list the contents of a data catalog after it is created, your Hook implementation can be as simple as:

```python
# <your_project>/src/<your_project>/hooks.py
import logging

from kedro.framework.hooks import hook_impl
from kedro.io import DataCatalog


class DataCatalogHooks:
    @property
    def _logger(self):
        return logging.getLogger(self.__class__.__name__)

    @hook_impl
    def after_catalog_created(self, catalog: DataCatalog) -> None:
        self._logger.info(catalog.list())
```

```{note}
The name of a module that contains Hooks implementation is arbitrary, and is not restricted to `hooks.py`.
```

We recommend that you group related Hook implementations under a namespace, preferably a class, within a `hooks.py` file that you create in your project.

#### [Registering your Hook implementations with Kedro](https://github.com/kedro-org/kedro/edit/main/docs/source/extend_kedro/regHookImp.md)
#### [Disable auto-registered plugins' Hooks](https://github.com/kedro-org/kedro/edit/main/docs/source/extend_kedro/disableHooks.md)