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
## docker search ubuntu
NAME            DESCRIPTION                                       STARS           OFFICAL   ......
ubuntu          Ubuntu is a Debian-based Ninux Operating s...     4656             [OK]
ubuntu-upstart  Upstart is an event-based replacement for ...     66               [OK]
.......

# STARS는 얼마나 즐겨찾는지를 나타냄
{% endhighlight %}
