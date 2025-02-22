# Pipelines

In machine learning, it is common to run a sequence of algorithms to process and learn from data. The entire ML lifecycle can be represented as a sequence of tasks and input/output dependencies in a workflow (aka DAG). This can all be packaged into what is called a *pipeline*.

ML Pipelines are a:
* Consistent way for data scientists to consume multiple phases and projects in AI lifecycle
* Composable layer, so different parts of the AI lifecycle can be snapped together like legos
* One-stop shop for people interested in training, validating, deploying and monitoring AI models

## Create an AI Pipeline
The simplest way to create a pipeline is to use [Kubeflow](https://www.kubeflow.org/). Kubeflow provides an SDK to create and execute pipelines.

1. Package your custom [components](../component-samples/README.md) into docker
   images, or use registered components here by just pulling the YAML specification
2. Create a python class for each component to describe interactions with their
   respective docker containers
3. Define the pipeline as a python function
4. Compile to pipeline.
    * This produces a YAML file compressed as a `.tar.gz`

For an in-depth guide to creating pipelines with Kubeflow, take a look at their
[documentation](https://www.kubeflow.org/docs/components/pipelines/sdk/component-development/).

## Upload an AI Pipeline
1. Click on the "Pipelines" link in left-hand navigation panel
2. Click on "Upload a Pipeline"
3. Select a file to upload (Must be `.tar.gz` or `.tgz` format)
4. Enter a name for the pipeline; Otherwise a default will be given

## Run an AI Pipeline

1. Under the "Pipelines" tab, select the pipeline
    * This will take you to pipeline "view" page
2. Click "Create run", and fill out the run details and parameters
3. Clicking "Start" will kick off the run
    * A history of finished / currently running pipelines will show up under
      the Experiments view in the "All runs" tab.
    * Clicking on the run row will show progress and output of each run.


## List of Sample Pipelines
* [Trusted AI Pipeline with AI Fairness 360 and Adversarial Robustness 360 components](https://github.com/kubeflow/kfp-tekton/tree/master/samples/trusted-ai)
* [Training and Serving Models with Watson Machine Learning](https://github.com/kubeflow/kfp-tekton/tree/master/samples/watson-train-serve#training-and-serving-models-with-watson-machine-learning)
* [Lightweight python components example](https://github.com/kubeflow/kfp-tekton/tree/master/samples/lightweight-component)
* [The flip-coin pipeline](https://github.com/kubeflow/kfp-tekton/tree/master/samples/flip-coin)
* [Hyperparameter tuning using Katib](https://github.com/kubeflow/kfp-tekton/tree/master/samples/katib)
* [Nested pipeline example](https://github.com/kubeflow/kfp-tekton/tree/master/samples/nested-pipeline)
* [Pipeline with Nested loops](https://github.com/kubeflow/kfp-tekton/tree/master/samples/nested-loops)
