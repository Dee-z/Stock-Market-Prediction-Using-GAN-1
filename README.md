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

# 1. Kiwoom API 로 주식 분봉데이터 수집
- 특징 : 조회제한 오류 발생..
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
4. 수집한 db → csv 파일로 내보내기
- DB Browser for SQLite 프로그램으로 파일>내보내기>csv파일로 

# 2. Creon API (대신증권) 로 주식 분봉데이터 수집 (추천★)  
- 특징 : 1분봉 2년치의 데이터까지 추출가능
1. CreonPlus(API) 설치 및 비대면계좌(모바일앱으로 하면 편함) 개설  
2. CreonPlus 및 소스실행시키는 프로그램 모두 **관리자 권한** 으로 설정  
  **관리자 권한 실행**으로 하지 않으면 연결오류 출력됨  
    
  source : https://github.com/gyusu/Creon-Datareader


# 파이토치로 훈련해보기
1. 파이토치 설치
> Permission error 가 뜨면 Prompt를 관리자 권한으로 실행시켜서 설치하면 해결 된다.
```
# CUDA 9.0
>conda install pytorch==1.1.0 torchvision==0.3.0 cudatoolkit=9.0 -c pytorch

# CUDA 10.0
>conda install pytorch==1.1.0 torchvision==0.3.0 cudatoolkit=10.0 -c pytorch

# CPU Only
>conda install pytorch-cpu==1.1.0 torchvision-cpu==0.3.0 cpuonly -c pytorch
```
2. 설치확인
```
>python
>>> import torch
```
  
# Reference
[대신증권 API](https://github.com/gyusu/Creon-Datareader)

[SQLite DB에 일봉 데이터 저장하기](https://wikidocs.net/5757)

[sqlite3 모듈 기초](https://wikidocs.net/5327)

[키움 Open api 조회제한](https://toptrader.tistory.com/3)

[키움 Open api 주식 알고리즘 테스트 프로그래밍](https://programmingfbf7290.tistory.com/entry/4-%EC%A3%BC%EC%8B%9D-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B6%88%EB%9F%AC%EC%98%A4%EA%B8%B0-%ED%82%A4%EC%9B%80-open-api-%EC%A3%BC%EC%8B%9D-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%ED%85%8C%EC%8A%A4%ED%8A%B8-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)

[퀀티랩 블로그](http://blog.quantylab.com/category/quant2.html)
