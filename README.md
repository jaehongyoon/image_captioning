### Introduction
The gRPC program designed as requested. The image sent through protocol buffer is manipulated from the server and sent back to client. Three rpc functions are provided as following.

* **RotateImage** Rotates Image as multiples of 90 degrees.

* **CustomImageEndpoint** Apply OpenCV seamlessClone function to synthesize two colored image.

* **GetImageCaption** Run RNN program in Python by calling Python module in server. Requires Image captioning python code from git ([instructions](https://github.com/jaehongyoon/image_captioning)). Run the 'main.py' module with COCO Training Image ([instructions] (http://cocodataset.org/#download)).

### System Description
The code was generated and compiled on Ubuntu 14.0.

### Prerequesites
* **Python** ([Source Code](https://www.python.org/downloads/))
* **Image captioing Module** ([instructions](https://github.com/jaehongyoon/image_captioning))
* **OpenCV** ([Source Code](https://github.com/opencv/opencv))
* **TensorFlow** ([instructions](https://www.tensorflow.org/install/install_sources))
* **gRPC** ([instructions](https://grpc.io/docs/quickstart/cpp.html#before-you-begin))

### Usage
* **grpc app** Makefile is provided. In order to compile the program type 
```shell
make
```
You will get _**server_ _**cliend_

The grpc applications (server/client) can be compliled using make file. On command prompt type "make." You will get "server" and "client" which are gRPC server and CLI test client. Run the server and client on command prompt and follow the instructions.

### Limitations/Issues
* **(1) Limitations and Issues** 

* **(2) Image Captioning** For image captioning, the server must have a pretrained model. To use the model file (*.pb), the user should first run the python code accordingly to the instruction ([instructions](https://github.com/jaehongyoon/image_captioning)). The model is then saved as "tmp/my_saved_model." Open the server.cpp and change the model file path accordingly to your system.
Unfortunately, the code crashed as restoring image caption in output tensor crash. Future version will ad Image captioning request as well.

