#### Disable auto-registered plugins' Hooks

You can disable auto-registered plugins' Hooks via the `settings.py` file as follows:

```python
# <your_project>/src/<your_project>/settings.py

DISABLE_HOOKS_FOR_PLUGINS = ("<plugin_name>",)
```

where `<plugin_name>` is the name of an installed plugin for which the auto-registered Hooks must be disabled.