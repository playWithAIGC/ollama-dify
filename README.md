# ollama-dify
Deploy Ollama and DIFY in Win11





# **Win11 本地部署****ollama 模型**



## **1.创建环境**

### **1.1安装llama.cpp**

## **`conda create -n ollama-dify python=3.11 conda activate ollama-dify pip install --pre --upgrade ipex-llm[cpp]`**

### **1.2运行llama.cpp的设置**

首先，应该创建一个要使用的 llama.cpp 目录，例如，使用以下命令创建一个 llama-cpp 目录并输入它。



```
mkdir llama-cpp

cd llama-cpp
```



### **1.3使用 IPEX-LLM 初始化llama.cpp**

请在 cmd 中以管理员权限运行以下命令。



```
init-llama-cpp.bat
```



init-llama-cpp 将创建llama.cpp可执行文件到当前目录的软链接，如果你想在其他地方使用这些可执行文件，不要忘记再次运行上面的命令。

### **1.4. 初始化 Ollama**

请在 Anaconda Prompt 中以管理员权限运行以下命令。



```
conda activate ollama-dify
init-ollama.bat
```





初始化完毕之后目录是这样的

![img](https://docs.qingque.cn/image/api/external/load/out?code=eZQDWzwKkGtbmutq6EQKZYU4k:-1063474097227392234eZQDWzwKkGtbmutq6EQKZYU4k:1720159520727&identityId=29Wjy2gAtoi)



## **2.运行** 

### **2.1运行ollama服务**

> 前置条件先安装[**安装oneAPI**](https://docs.qingque.cn/d/home/eZQB1ATDp97-3PDUxdOCBUbVP?identityId=29Wjy2gAtoi)

为确保模型的所有层都在 Intel GPU 上运行

创建run.bat

内容如下：



```
set OLLAMA_NUM_GPU=999
set no_proxy=localhost,127.0.0.1
set ZES_ENABLE_SYSMAN=1set SYCL_CACHE_PERSISTENT=1
call "C:\Program Files (x86)\Intel\oneAPI\setvars.bat"
ollama serve
```



![img](https://docs.qingque.cn/image/api/external/load/out?code=eZQDWzwKkGtbmutq6EQKZYU4k:7054727328273855680eZQDWzwKkGtbmutq6EQKZYU4k:1720159520728&identityId=29Wjy2gAtoi)



### **2.2****下载LLM模型**

首先去ollama模型库去查看model

网址：https://ollama.com/library

这里以千问的qwen1.5为例子
