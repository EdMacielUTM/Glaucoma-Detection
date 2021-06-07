# Glaucoma-Detection
Machine Learning solution for glaucoma detection using transfer learning.



## Docker Image

To avoid CUDA/CuDNN/Tensorflow compatibility issues a Docker image is
being used. Use the following command to do so.

> If your docker daemon does not support GPUs you should not include --gpus all
> option.

```
$ docker run -d \
  --name {container-name} \
  -p 8888:8888 \
  --gpus all \
  -it \
  -v {path/to/repo}:/tf/notebooks \
  tensorflow/tensorflow:2.3.2-gpu-py3-jupyter
```

## Opening the notebook

In order to open the Jupyter notebook and reproduce the work previously 
made in this repo, it is required to open the link available through the
docker container's log registry.

```
$ docker logs {container-name}
```

The command above should yield a link similar to the following.

```
 http://127.0.0.1:8888/?token={token}
```

## Executing the notebook

The notebook itself contains the necessary commands to install the required 
dependencies in order to execute its code entirely, no further installation
required. However, the datasets used for training are required and should be
provided within their respective subdirectories as .rar files as shown below.

```
.
├── augmented
│   └── dataset.rar
├── simple
│   └── dataset.rar
└── glaucoma.ipynb
```

> Currently, this repo does not provide the required datasets. Please contact
> the author of this repo at `cedmaclaz@gmail.com` for further details.
