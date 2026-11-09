# Experiment Tracking with MLflow
Experiment tracking is the systematic process of recording important information about each ML training run, including code versions, data, parameters, metrics, and artifacts. It enables reproducibility, comparison between experiments, and informed decisions about which model to deploy.

**MLflow** is an open-source platform for managing the ML lifecycle, providing tools for experiment tracking, code packaging, and model deployment.

In MLflow, an **experiment** is a collection of related training executions, while each individual execution is called a **run**. Every run tracks three key components:
* **Parameters**: Input settings and hyperparameters that control training, such as the learning rate, random seed, or number of estimators.
* **Metrics**: Quantitative measures used to evaluate model performance, such as training loss, validation accuracy, and precision.
* **Artifacts**: Output files generated during training, including saved model files, plots, and other data files.

By automating this tracking process, MLflow eliminates the need for manual record-keeping and provides a structured, queryable history of experiments. This makes it possible to compare different approaches, justify model selection with concrete evidence, and reproduce previous experiments to validate results.

These tracked experiments establish a reliable foundation for the ML lifecycle, supporting higher-level tasks such as automated model deployment.