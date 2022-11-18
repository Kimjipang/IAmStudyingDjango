 ## Python & Django 설치
- **Django로 개발을 하기 위해서는 Python을 다운받아야 한다.(python은 3.8 이상의 버전을 권장한다고 함.)**

  -> Python Download Link : https://www.python.org/

  (Mac os 기준 homebrew를 사용하면 굉장히 쉽게 다운 가능)
  
  

- **다운로드가 잘 되었는지 확인하려면 terminal에서 python3를 치면 된다.**


  <img width="600" alt="스크린샷 2022-11-17 오후 7 44 10" src="https://user-images.githubusercontent.com/91196025/202426483-f1bb9d7c-fe4e-4d4d-893f-8bcb6511ee1a.png">

  ​	**필자는 3.11.0 버전이다**
  
  

- **원하는 위치에 폴더를 생성한다.**

  -> 필자는 잘 보이도록 PC 바탕화면에 생성했다.



- **다운로드 한 VSC를 구동시키고 생성한 폴더를 연다.**

  -> [파일] - [폴더 열기]

  <img width="700" alt="스크린샷 2022-11-17 오후 7 45 24" src="https://user-images.githubusercontent.com/91196025/202426528-d2999552-da25-4cfc-af66-6de46e33e9b8.png">
  
- VSC의 터미널(ctrl + shift + `(~)를 입력해도 가능)을 켜서 가상 환경인 virtual environment를 구축하고, 구동시켜야 한다.
```python
python3 -m venv myvenv # myvenv는 본인이 구축하고 싶은 venv의 이름으로 하면 된다.
source myvenv/bin/activate # 구축한 venv를 실행하는 코드
```
<img width="600" alt="스크린샷 2022-11-17 오후 7 59 45" src="https://user-images.githubusercontent.com/91196025/202429120-15ebbbf5-172c-4401-b984-de1e5b1e8e15.png">


- 이제 Django를 설치해야 한다.

  ```python
  pip install django~=3.2.10 # 3.2.10 버전의 장고 설치
  ```

  <img width="600" alt="스크린샷 2022-11-18 오전 10 59 03" src="https://user-images.githubusercontent.com/91196025/202604411-44de520b-101e-4133-8841-4d5fde9f8635.png">

- Django 프로젝트 생성 

  ```python
  django-admin startproject myweb . # myweb은 만들고 싶은 프로젝트 이름으로 설정하면 된다.
  ```

- 프로젝트 내 app 생성

  ```python
  python manage.py startapp login # login이라는 이름으로 app 생성
  # app name이 login인 것으로 보아 login 기능을 하는 기능들을 담는 곳이라 유추할 수 있다.
  ```

- 프로젝트 실행

  ```python
  python manage.py runserver 
  ```

  





