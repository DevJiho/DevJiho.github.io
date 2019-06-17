---
layout: post
title:  "도커 이미지"
date:   2019-06-17 12:35:00 +0900
categories: Server/DOCKER
---
# 도커 이미지
모든 컨테이너는 이미지를 기반으로 생성된다.
도커는 도커 허브라는 중앙 이미지 저장소에서 이미지를 내려받는다. (도커 허브는 도커가 공식적으로 제공하고 있는 이미지 저장소로서, 도커 계정을 가지고 있다면 누구든지 이미지를 올리고 내려받을 수 있음.)
도커 허브는 누구나 이미지를 올릴 수 있기 때문에 공식 라벨이 없는 이미지는 사용법을 찾을 수 없거나 동작 안 할 수 있음.


도커 허브에 어떤 이미지가 있는지 확인하기 위해 docker search라는 명령어를 사용할 수 있다.
{% highlight ruby %}
## #docker search ubuntu
NAME            DESCRIPTION                                       STARS           OFFICAL   ......
ubuntu          Ubuntu is a Debian-based Ninux Operating s...     4656             [OK]
ubuntu-upstart  Upstart is an event-based replacement for ...     66               [OK]
.......
# STARS는 얼마나 즐겨찾는지를 나타냄
{% endhighlight %}

docker search를 통해 검색한 이미지를 pull로 내려받아 사용할 수도 있지만 도커로 개발하는 많은 경우에는 컨테이너에 애플리케이션을 위한 특정 개발 환경을 직접 구축한 뒤 사용자만의 이미지를 직접 생성해야 할 것이다. 이를 위해 컨테이너 안에서 작업한 내용을 이미지로 만드는 방법이 필요하다.

다음 명령어를 입력해 이미지로 만들 컨테이너를 생성
{% highlight ruby %}
## #docker run -i -t --name commit_test ubuntu:14.04
root@663f5ee58b6c:/# echo test_first! >> first

# first라는 파일을 만들어서 ubuntu:14.04 이미지로부터 변경 사항을 만들었다면 컨테이너에서 호스트로 빠져나와 docker commit 명령어를 입력해 컨테이너를 이미지로 만든다. docker commit 명령어의 형식은 다음과 같다.
## # docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
{% endhighlight %}
