# LlamaCPP GPU Setting Manual


### 개요:
**llama-cpp-python**을 활용하면 손쉽게 **llama2/LLM** 모델들을 보다 쉽게 불러와 사용할 수 있다.

CPU 나 GPU 를 사용하여 LLM모델을 사용 가능한데, 성능이 좋은 GPU가 컴퓨터에 내장되어 있다면, 당연히 GPU를 사용하여 응답받는 (text gen) 속도를 대폭 상승시킬 수 있다. 

따라서 llama-cpp-python을 GPU에 연결하여 **윈도우11** 컴퓨터에서 사용하는 방법에 대해 설명한다. (Nvidia GPU - CUDA 설치/연결에 관해서는 이미 해결된 상태라 여기고 설명한다.)

<br>


## Prerequisites:
- **Visual Studio** (보라색):
    -  C++ CMake tools for Windows
    -  C++ core features
    -  Windows 10/11 SDK
  
- **CUDA Toolkit** (CMD 명령어로 확인):
    - nvcc --version
    - nvidia-smi
  
- **CUDA_PATH** 환경변수 추가되있느지 확인

<br>


## Installation:
구축한 가상환경에 들어가 아래 명령어 순차적 실행:

```python
set CMAKE_ARGS=-DLLAMA_CUBLAS=on
set FORCE_CMAKE=1
pip install llama-cpp-python --force-reinstall --upgrade --no-cache-dir
```

마지막 명령어에 **--verbose** 를 추가하면 cuBLAS/CUDA가 제대로 설치/연결됬는지 확인가능하다.

만약 제대로 cuBLAS가 설치중에 세팅되지 않았으면, **"cuBLAS not found"** 라고 에러메세지가 포함되는데
GPU로 연결이 되지않는 llama-cpp-python이 설치된 것이다.

이런경우에는 CUDA Toolkit이 환경변수에 제대로 잡혀있는지 확인하고 uninstall 후 다시 재설치 해주면 된다.

<br>


## Use:
langchain 이나 llama_cpp 를 사용하여 GPU - cuda가 잘 작동하는지 확인.



**연결확인 : llama_cpp**
```python
from llama_cpp import Llama
llm = Llama(model_path="model.gguf", n_gpu_layers=30, n_ctx=3584, n_batch=521, verbose=True)

# adjust n_gpu_layers as per your GPU and model
output = llm("Q: Largest Country in the World?", max_tokens=32, stop=["Q:", "\n"], echo=True)
print(output)
```

GPU가 정상적으로 잘 작동되고 있다면 출력되는 변수 중 **BLAS=1** 이라고 표기된 것을 볼 수 있을것이다. ~~만약 제대로 작동되지 않는다면 BLAS=0~~
