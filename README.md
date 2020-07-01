# Stock-Market-Prediction-Using-GAN
Stock Market Prediction on High-Frequency Data Using Generative Adversarial Nets  
  
# Keras without Nvidia-GPUs with PlaidML 
## - Using AMD-GPU_RX580
Keras is an open source neural network library written in Python.  
Running it over TensorFlow usually requires Cuda which in turn requires a Nvidia GPU.  
PlaidML is an advanced and portable tensor compiler for enabling deep learning on laptops, embedded devices, or other devices where the available computing hardware is not well supported or the available software stack contains unpalatable license restrictions.
It does not require the usage of CUDA or cuDNN on Nvidia hardware, while achieving comparable performance.  

케라스는 파이썬으로 작성된 오픈소스 신경망 라이브러리입니다.  
TensorFlow를 통해 실행하려면 일반적으로 Cuda가 필요하며 Nvidia GPU가 필요합니다.  
PlaidML은 AMD-GPU로 딥러닝을 가능하게 하는 advanced and portable한 Tensor Compiler입니다.  
**AMD-GPU로 Nvidia-GPU와 비슷한 성능을 달성**하면서 Nvidia GPU, CUDA, cuDNN을 사용할 필요가 없습니다!  

# Prediction Model
![GAN-FD](https://github.com/ojkk371/Stock-Market-Prediction-Using-GAN/blob/master/fig/GAN-FD-structure.png?raw=true)

# Kiwoom API 로 주식 분봉데이터 수집
1. 키움증권 가입 & 키움증권 Open API 사용허가 & Open API 모듈 설치
2. Anaconda 32-bit 설치
```
# 아나콘다 32bit로 강제설정
>set CONDA_FORCE_32BIT

# 가상환경 설치
>conda create -n 가상환경이름 python=3.5.6 anaconda

# 파이썬 3.5버전을 사용한 이유는 추후에 zipline을 사용하기 위해서입니다.
```
3. 설치한 가상환경의 bit 확인
```
# 가상환경 진입
>conda activate 가상환경이름

# 비트확인
>python
>>> import platform
>>> print(platform.architecture())

결과: ('32bit','WindowsPE') 라고 떠야 잘된것.
```
