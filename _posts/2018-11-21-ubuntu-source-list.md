---
title: Ubuntu 소프트웨어 업데이트 서버를 daum(kakao)로 변경(sources.list)
date: 2018-11-21 06:00:00 +0900
last_modified_at: 2018-11-18 06:00:00 +0900
categories:
- IT일반
tags:
- Ubuntu
- 우분투
- 업데이트서버
- sources.list
- apt-get
---

최초 Ubuntu 설치 시 Ubuntu SW 업데이트를 위한 서버가 kr.archive.ubuntu.com 으로 되어있습니다.<br>
이 주소를 그대로 사용할 수도 있으나, 속도가 제대로 나지 않습니다.<br>
daum 서버 (daumkakao로 변경) 로 설정하는 것이 좋습니다.

CTRL + ALT + T 를 입력하여 터미널을 실행합니다.<br>
vi를 통해 source.list 를 수정합니다. <br>
(vi가 익숙하지 않다면 gedit 등의 다른 편집기를 사용해도 됩니다.)

관리자 권한으로 수정이 가능한 파일이기 때문에 sudo로 열어주어야 합니다.

```bash
sudo vi /etc/apt/sources.list
```

":"를 눌러 명령어 입력모드로 가서 아래 키워드를 입력하여 문자열 찾아 바꾸기를 합니다.<br>
파일 내부에서 'kr.archive.ubuntu.com' 문자열을 'ftp.daumkakao.com' 으로 변경하는 명령입니다.

```bash
:%s/kr.archive.ubuntu.com/ftp.daumkakao.com
```

변경이 되었다면 다시 ":"를 눌러 명령어 입력모드로 들어가 wq를 입력하여 vi를 저장하고 종료합니다.

```bash
:wq
```

sudo apt-get update를 해보면 daumkakao server를 통해 업데이트 되는 것을 볼 수 있습니다.

```bash
sudo apt-get update
```
