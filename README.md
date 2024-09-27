# 매우매우 기본적인 CS 지식을 정리합니다!

## 1. docker

### docker 설치 확인: docker -version

### docker 개념!

docker는 같은 실행환경을 보장해주기 위해서 사용하는 것!

#### **image**: 어떤 운영체제나 패키지를 사용할 것인지를 정해주는 개념 / 읽기 전용 템플릿

image는 이름과 태그로 구성되는데, ubuntu(os name)과 20.02(tag)과 같이 구성된다. 절대 변하지 않는 읽을 수만 있는 요소이다.

#### **container**: image에 담긴 설명을 바탕으로 실제로 만들어진 가상환경 / 쓰기 가능 템플릿

만약에 어떤 행동을 한다면(패키지 설치나 파일 복사 등등) 그것들이 layer로 만들어진다!(layer는 간단하게 변경기록이라고 생각하면 된다) 

즉, image와 container는 요리책과 요리의 관계이다!(요리책을 보고 실제 요리를 만드는 것으로 생각하면 편하다)

### docker의 전형적인 사용방식

docker는 다음과 같은 방식으로 사용한다.

1. 이미지 만들기: ```docker pull ubuntu:latest #for create ubuntu os env```
2. 만들어진 이미지 확인: ```docker images```
3. 이미지를 바탕으로 container 실행 ```docker run -it --name {container name} ubuntu:latest```
4. 이제 container를 이용해 layer를 쌓아보자!
```
apt update
apt install {packages}
pwd # whatever you want in ubuntu terminal!
```
5. container 안에 있는 경로로 접근하고 싶다면, {container name):{container path}와 같이 작성해주면 된다.
```
docker cp ./ my_container:./dir1/
``` 
