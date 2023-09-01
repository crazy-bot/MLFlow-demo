# MLFlow-demo
This repository contains a demo of MLFlow for end to end life cycle of ML projcets

# Introduction

In this repository, I have used MLFlow for tracking machine learning experiments, registering model in MLFlow model registry and write code how to select best performing model based on logged metric, transition the selected model from one stage to another (for e.g: dev to staging and staging to production). Further how to load the model from model registry and serve predictions.

# Data

I used Fashion-MNIST dataset for this demo. download data from [data](https://www.kaggle.com/datasets/zalando-research/fashionmnist). Extract the contents in "data" folder.

# MLFlow Tracking

1. File store as back end storage running in local
```
mlflow ui
```

2. Database backend ane tracking server in local. DB backend is needed to use MLFlow Registry. I use sqlite database in my machine. It can be postgres, mysql or any cloud database.

```
mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root ./artifacts --host 0.0.0.0 --port 5000
```

3. mlflow serve as endpoint

mlflow models serve --model-uri models:/cnn/Staging -p 1234 --no-conda


