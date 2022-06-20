# Hooks

## Introduction

Hooks are a mechanism to add extra behaviour to Kedro's main execution in an easy and consistent manner. Some examples might include:

* Adding a log statement after the data catalog is loaded
* Adding data validation to the inputs before a node runs, and to the outputs after a node has run. This process makes it possible to integrate with other tools, such as [Great-Expectations](https://docs.greatexpectations.io/en/latest/)
* Adding machine learning metrics tracking, e.g. using [MLflow](https://mlflow.org/), throughout a pipeline run

## Concepts

A Hook consists of a [Hook specification](https://github.com/kedro-org/kedro/edit/main/docs/source/extend_kedro/hookspec.md), and [Hook implementation](https://github.com/kedro-org/kedro/edit/main/docs/source/extend_kedro/hookimp.md). To add Hooks to your project, you must:

* Create, or modify, the file `<your_project>/src/<package_name>/hooks.py` to define a Hook implementation for an existing Kedro-defined Hook specification
* Register your Hook implementation in the [`src/<your_project>/settings.py`](../kedro_project_setup/settings.md) file under the `HOOKS` key

## Under the hood

Under the hood, we use [pytest's pluggy](https://pluggy.readthedocs.io/en/latest/) to implement Kedro's Hook mechanism. We recommend you read their documentation for more information about the underlying implementation.

## [Examples](https://github.com/kedro-org/kedro/edit/main/docs/source/extend_kedro/hookExamples.md)
