# 프로젝트 진행 - 파일 서버 만들기!

---

## 프로젝트 개요

### preview

- 상황
  - 원격지에서 파일을 내 컴퓨터로 얼리거나 내 컴퓨터에 있는 파일을 다운로드, 필요 없는 파일 제거 등 파일 관리
- 코드

  - https://github.com/neltia/Flask-FileService-app

- 파일 업로드
  - 파일 목록 위 업로드할 파일 선택 버튼을 배치
- 파일 업로드 확인
  - 성공 메시지 띄우기
- 파일 업로드 검증
  - 업로드 된 파일이 없을 때 제출 버튼을 눌렀다면 제출이 안 되게 방지
- 파일 정보 확인
  - 파이썬의 OS 운영체제 모듈과 datatime 모듈(내부모듈)로 쉽게 파일 정보 확인 가능
- 파일 목록 나열
  - 파일 확장자/파일 이름/만든 날짜/마지막 수정 날짜/파일 크기 등
- 파일 다운로드
  - 나열된 목록에서 파일 이름을 선택하면 해당 파일 다운로드, 삭제 버튼을 누르면 삭제되도록 기능 추가
  - 추가로 잘못된 페이지로 접근하면 페이지 비정상 접근 메시지 표시

### project tree

- 완성될 프로젝트 구성 내용
  - static: image
  - templates: HTML 템플릿
  - uploads: 파일이 업로드 될 폴더

### Library

- 프로젝트 사용 라이브러리
  - 다음 라이브러리가 사용
    `from flask import flask, rander_tamplate, request, redirect, url_for, send_file`
    `from flask_wtf import FlaskForm`
    `from flask_wtf.file import secure_filename`
    `from werkzeug.utils import secure_filename`
    `import os, datetime, time`

---

## 파일 업로드

### Tech. 파비콘 설정

- 파비콘: Favicon, 인터넷 웹 브라우저의 주소창에 표시되는 웹 페이지를 대표하는 아이콘
  ![alt text](image_ch4/image.png)
- 표시할 아이콘 준비
  - FlatIcon: https://www.flaticon.com/
    - 무료 픽토그램 제공
  - convertico: https://convertico.com/
    - 이미지를 .ico 파일로 변환

### Tech.Jinja2 block과 extends

- base.html 구성하기
  - 보다 복잡한 프로젝트를 구성하면 내용을 간소화하고 분할하는 작업이 필수
  - 보통 base.html을 만들어 모든 HTML 파일의 공통적인 부분을 기록함
    - extends로 다른 html에서 base를 상속받도록!

### Tech.Flask 파일 업로드

- 파일을 선택해 업로드하면 파일 서버가 실행되는 경로의 uploads 폴더에 저장
- 파일 업로드 처리를 위한 모듈 - request, secure_filename
  ![alt text](image_ch4/image-1.png)
- 파일 업로드 페이지 이동
  ![alt text](image_ch4/image-2.png)
- 파일 업로드 처리
  ![alt text](image_ch4/image-3.png)
