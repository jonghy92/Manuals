<!-- GPU Setting -->
# NVIDIA GPU Setting Manual

### 개요:
딥러닝을 하기 위해선 __"Nvidia GPU"__ 가 필요로 하며, __"전용 GPU 메모리"__ 가 모델 및 데이터를 올려 작동/처리하는데 중요하게 작용된다. (딥러닝 모델이 무거워 메모리보다 더 많은 용량을 차지한다면 모델을 제대로 사용/학습시킬 수 없다)


따라서 Nvidia GPU를 가진 컴퓨터를 가지고 있다면 Nvidia에서 제공하는 몇가지 파일을 먼저 설치 후 (Nvidia Driver & CUDA Toolkit) 버전을 확인하여 Pytorch나 Tensorflow에서 제공하는 특정 버전에서 지원되는 프레임워크를 설치하여 사용하면 된다. (본 매뉴얼에서는 Window OS - Pytorch 환경 기준으로 설명한다)

<br>


## Step 1 : GPU 모델 확인
우선적으로 컴퓨터/노트북에 내장된 GPU의 모델명을 확인해야 한다.


**CMD(Terminal):**
```
nvidia-smi -L
nvidia-smi
```

<br>

**시스템:** <br>
```
윈도우키 --> dxdiag 검색--> 디스플레이2
```


<br>

## Step 2 : CUDA 드라이버 설치:
확인된 GPU 모델명을 지원하는 **Nvidia GPU Driver**를 Nvidia 웹으로 이동해서 찾아 설치해주어야 한다. (CUDA Compute Capability 가 3.5 이상인 GPU 카드만 지원한다고 하는데, 요즘 나오는 신형 노트북/PC는 기본적으로 3.5 이상임)

**Nvidia 드라이버를 설치하기:**
- https://www.nvidia.com/Download/index.aspx?lang=kr


<br>

## Step 3 : CUDA Toolkit 설치:
Meta Pytorch 웹으로 이동하여 CUDA 버전을 우선적으로 확인해야 한다. 나중에 다운로드 받을 때 자신의 컴퓨터의 환경에 따라 받아야하는 버전이 달라진다. (다른 사람이 만든 프로젝트를 사용 시에는, 그 사람의 환경과 동일하게 버전 및 OS를 주는걸 추천)

<br>

```
PyTorch Build : Stable (2.1.2)
Your OS : Windows
Package Pip
Language : Python
Compute Platform : CUDA 12.1
Run this Command : pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```
<br>

여기서 보면 최신 파이토치가 현재 **"CUDA 12.1"** 버전을 지원한다고 알 수 있으므로, Nvidia 웹사이트로 이동하여 CUDA 12.1 버전의 Toolkit을 찾아 다운로드 해야한다.

1. CUDA Toolkit 설치페이지로 이동
   - https://developer.nvidia.com/cuda-toolkit-archive
2. 컴퓨터 혹은 본인 프로젝트에 맞는 CUDA Toolkit 파일/버전을 찾아 설치

3. 제대로 설치가 완료되면 CMD(Terminal)에서 확인 가능:
   - nvcc --version

<br>


## Step 4 : CuDNN 설치:
마지막으로 CUDA가 설치된 경로로 이동해서 CuDNN을 설치하여 넣어주어야 한다. CuDNN을 설치하려면 Nvidia 회원가입이 필요하다.

**CuDNN 설치하기:**
- https://developer.nvidia.com/cudnn

<br>

**CUDA 12.1** 버전을 사전에 다운로드 받았기 때문에, **CuDNN 12.x** 버전(Windows 용)을 다운로드 받았다. 이렇게 다운로드 받은 파일을 압축해제 하면
1. LICENSE
2. include
3. lib
4. bin

파일들이 나오는데, 이 파일들을 복사하여 **CUDA > v12.1 폴더 안에**에 붙여넣기/덮어씌어주기를 해준다.
```
경로:
내pc > C드라이브 > Program Files > NVIDIA GPU Computing Toolkit > CUDA > 12.1
```

<br>


## Step 5 : 시스템 환경 변수 설정
앞서 설치한 CUDA의 환경 변수 몇가지를 시스템에 추가를 해주어야 한다.


**시스템 환경 변수 편집/추가:**
```
경로:
윈도우키 --> 시스템 환경 변수 편집 --> 환경 변수 --> Path 추가

추가:
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.1\bin
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.1\extras
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.1\include
```


<br>

## Step 6 : Pytorch GPU 동작 확인
마지막으로, 12.1 버전으로 작동하는 Pytorch를 OS에 맞게 설치해주면 된다. <br>

**Pytorch Install:**
> pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121

<br>

파이썬 환경에 다운로드가 완료되면:

```python
import torch
torch.cuda.get_device_name(0)
torch.cuda.is_available()
torch.__version__
```
상위 명령어를 통해 버전 및 컴퓨터의 GPU를 제대로 읽어오는지 확인하면 최종 마무리가 완료된다.


<br>

## 비고 :
GPU를 사용한 후에 **전용 GPU 메모리(VRAM)** 를 비워줄때가 필요하다. 학습/예측이 끝났음에도 불구하고 만약 메모리가 계속 할당되어있다면 다른작업을 할 시 당연히 에러가 난다. (혹은 사용후 다른 AI모델을 import 할 때....)

따라서 GPU VRAM을 모니터링 하여 필요시 메모리 초기화를 해주는 파이썬 라이브러리가 있어 사용하면 좋다.

**설치 및 사용법:**
```python
# 라이브러리 설치
pip install numba
```

```python
# library import
from numba import cuda

# GPU VRAM Clear (메모리 비우기)
device = cuda.get_current_device()
device.reset()
```





