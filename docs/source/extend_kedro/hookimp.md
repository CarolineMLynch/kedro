### Hook implementation

You should provide an implementation for the specification that describes when you want to inject additional behavior. The Hook implementation should have the same name as the specification. The Hook must provide a concrete implementation, with a subset of the corresponding specification's parameters (you need not use them all).

To declare a Hook implementation, use the `@hook_impl` decorator.

For example, the full signature of the [`after_data_catalog_created`](/kedro.framework.hooks.specs.DataCatalogSpecs) Hook specification is:

```python
@hook_spec
def after_catalog_created(
    self,
    catalog: DataCatalog,
    conf_catalog: Dict[str, Any],
    conf_creds: Dict[str, Any],
    save_version: str,
    load_versions: Dict[str, str],
) -> None:
    pass
```