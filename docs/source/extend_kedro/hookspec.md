### Hook specification

Kedro defines Hook specifications for particular execution points where users can inject additional behaviour. Currently, the following Hook specifications are provided in [kedro.framework.hooks](/kedro.framework.hooks):

* `after_catalog_created`
* `before_node_run`
* `after_node_run`
* `on_node_error`
* `before_pipeline_run`
* `after_pipeline_run`
* `on_pipeline_error`
* `before_dataset_loaded`
* `after_dataset_loaded`
* `before_dataset_saved`
* `after_dataset_saved`

The naming convention for non-error Hooks is `<before/after>_<noun>_<past_participle>`, in which:

* `<before/after>` and `<past_participle>` refer to when the Hook executed, e.g. `before <something> was run` or `after <something> was created`.
* `<noun>` refers to the relevant component in the Kedro execution timeline for which this Hook adds extra behaviour, e.g. `catalog`, `node` and `pipeline`.

The naming convention for error hooks is `on_<noun>_error`, where:

* `<noun>` refers to the relevant component that throws the error in the Kedro execution timeline.

[kedro.framework.hooks](/kedro.framework.hooks) details the full specifications for which you can provide an implementation to inject additional behaviors.


#### CLI hooks

Lastly, Kedro defines a small set of CLI hooks that inject additional behaviour around execution of a Kedro CLI command:

* `before_command_run`
* `after_command_run`

The [`kedro-telemetry`](https://github.com/kedro-org/kedro-plugins/tree/main/kedro-telemetry) plugin relies on these commands under the hood, to be able to collect CLI usage statistics.