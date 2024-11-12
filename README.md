# mlflow-test

Data Sorce: https://archive.ics.uci.edu/dataset/109/wine

1. Install mlflow using the command:
```bash
pip install mlflow
```
2. To start the mlflow server use the command:

```bash
mlflow server --backend-store-uri <foldername> --default-artifact-root <foldername> --host 127.0.0.1 --port <port_number>
```

Replace the `<foldername>` with the directory where you want to store metadata and artifacts.

3. This is the sample view of the mlflow UI.

![Screenshot 2024-11-11 203049](https://github.com/user-attachments/assets/c9540562-9fa3-4de1-839b-c6e56f989e81)

4. You can set you experiment with some specific or all will be logged/tracked in "Default" name.

```py
mlflow.set_experiment(<experiment_name>)
```

Replace the `<experiment_name>` with the experiment name of your choice.

5. After the training has been completed, we can log all the metrics, params and model in mlflow.

```py
mlflow.log_param(key="alpha", value=alpha)
mlflow.log_param(key="l1_ratio", value=l1_ratio)
mlflow.log_metric(key="rmse", value=rmse)
mlflow.log_metrics({"mae": mae, "r2": r2})
mlflow.log_artifact(data_path_red_wine)

print("Save to: {}".format(mlflow.get_artifact_uri()))

mlflow.sklearn.log_model(lr, 'model')
```
