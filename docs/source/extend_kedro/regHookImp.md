#### Registering your Hook implementations with Kedro

Hook implementations should be registered with Kedro using the [`<your_project>/src/<package_name>/settings.py`](../kedro_project_setup/settings.md) file under the `HOOKS` key.

You can register more than one implementation for the same specification. They will be called in LIFO (last-in, first-out) order.

The following example sets up a Hook so that the `after_data_catalog_created` implementation is called every time a data catalog has been created.

```python
# <your_project>/src/<your_project>/settings.py
from <your_project>.hooks import ProjectHooks, DataCatalogHooks

HOOKS = (ProjectHooks(), DataCatalogHooks())
```

Kedro also has auto-discovery enabled by default. This means that any installed plugins that declare a Hooks entry-point will be registered. To learn more about how to enable this for your custom plugin, see our [plugin development guide](plugins.md#hooks).

```{note}
Auto-discovered Hooks will run *first*, followed by those specified in the `settings.py` file.
```