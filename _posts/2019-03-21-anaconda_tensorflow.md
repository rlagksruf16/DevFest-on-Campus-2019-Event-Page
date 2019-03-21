---
layout: post
title: Docker에서 Anaconda 가상환경에 tensorflow, tensorflow-gpu 설치하기
subtitle: 
tags: [develop]
comments: true
---

Docker 새롭게 머신러닝 환경을 세팅하는데 나와 같은 고생을 하지 않기를 바라면서 글을 작성합니다.  

## Anaconda 가상환경 설치

```
cd ./home/anaconda

curl -O https://repo.anaconda.com/archive/Anaconda3-5.2.0-Linux-x86_64.sh

sha256sum Anaconda3-5.2.0-Linux-x86_64.sh

bash Anaconda3-5.2.0-Linux-x86_64.sh
```
<hr>  

```
Do you wish to proceed with the installation of Microsoft VSCode? [yes|no]
```
이 과정에서는 no를 누르시면 됩니다.  
(docker 환경에서 vscode를 쓰지 않기 때문에 설치하지 않습니다.)


이 외의 모든 설치 과정에서 yes를 하시면 됩니다.

설치 완료 후 아래 구문을 실행합니다.
```
source ~/.bashrc

//아나콘다 버전확인
conda --version

//아나콘다 업데이트
conda update conda
```
<hr>

## 가상환경 만들기
```
//가상환경 생성
//cpu 
conda create --name [가상환경이름] python=3.X(원하는 버전) tensorflow
//gpu 
conda create --name [가상환경이름] python=3.X(원하는 버전) tensorflow-gpu

//위 둘 중 하나를 한 후
source ~/.bashrc

//가상환경 실행
source activate [가상환경이름]
```

잘못된 부분이 있다면 언제든 댓글 혹은 이메일로 피드백 해주시면 빠르게 수정하겠습니다.

[참조 링크]:https://ufris.tistory.com/5
[참조 링크]:https://goodtogreate.tistory.com/entry/TensorFlow-GPU-%EB%B2%84%EC%A0%84-%EC%9A%B0%EB%B6%84%ED%88%AC-1604%EC%97%90-%EC%84%A4%EC%B9%98-%ED%95%98%EA%B8%B0