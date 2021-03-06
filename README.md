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

https://dataplay.tistory.com/4?category=845492

https://data-newbie.tistory.com/466

https://github.com/Gorosia/Stock_Prediction_Basic

https://dreamgonfly.github.io/2018/03/17/gan-explained.html

https://www.hindawi.com/journals/mpe/2018/4907423/

[PyTorch 사용법](https://greeksharifa.github.io/pytorch/2018/11/02/pytorch-usage-01-introduction/)
