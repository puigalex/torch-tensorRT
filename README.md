# Optimizar modelos de PyTorch con TensorRT y torch
## Estas son las ligas mencionadas en el video de [AMP tech en YouTube]():

1) [Docker](https://www.docker.com/)
2) [Nvidia Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#installation-guide)
3) [Documentacion de torch-tensorRT](https://pytorch.org/TensorRT/)
4) [Git Pytorch-tensorrt](https://github.com/pytorch/TensorRT)
5) [NGC](https://catalog.ngc.nvidia.com/)


## La lista de comandos mencionados en el video son los siguientes:
### Clonar el repositorio
```
git clone https://github.com/pytorch/TensorRT.git
```
Si quieres seguir el notebook que se muestra en el video de Youtube, descarga [este cuaderno]() o el **[repositorio]()** y colocalo en el directorio raiz del reporsitorio de TensorRT 

### Descargar la imagen de pytorch con tensor-rt
```
docker pull nvcr.io/nvidia/pytorch:22.05-py3
```

### Correr contenedor con la imagen descargada. 
Al correr este comando, uno debe de estar posicionado en la carpeta donde clono el repositorio pues el volumen compartido entre la computadora host y el contenedor estara en $PWD, también se puede poner una direccion en especifico en vez de $PWD

```
docker run --gpus=all --rm -it -v $PWD:/Torch-TensorRT --net=host --ipc=host --ulimit memlock=-1 --ulimit stack=67108864 nvcr.io/nvidia/pytorch:22.05-py3 bash
```

### Correr el Jupyter notebook con el código del video
Una vez que se está dentro del contenedor creado en el paso anterior, este comando te va a permitir acceder al cuaderno desde el explorador. El cuaderno en especifico que se ve en el video de Youtube lo puedes descargar de aqui y colocarlo en el directorio raiz del repositorio de Torch-TensorRT.

Otra opción es correr el notebook original de repositorio que está ubicado en /Torch-TensorRT/notebooks


```

jupyter notebook --allow-root --ip 0.0.0.0 --port 8888

```
