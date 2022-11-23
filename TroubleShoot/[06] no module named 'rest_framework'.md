## no module named 'rest_framework'



#### Issue

- DRF 개발을 해보기 위해 Django REST Framework을 install 하려고 했다.

- 설치를 한 후 settings.py의 INSTALLED_APPS에도 설치된 앱을 등록하였다. 

  ```python
  pip install djangorestframework
  ```

<img width="600" alt="스크린샷 2022-11-23 오전 10 50 22" src="https://user-images.githubusercontent.com/91196025/203457241-f777fc81-2411-47f3-b40d-2309d2f8b41c.png">

- 그러고 난 후에 runserver를 해보니 다음과 같은 에러가 나타났다.

  ```markdown
  > no module named 'rest_framework'
  ```

  

#### Reason Why?

- install도 확실히 해주었고 앱도 등록도 제대로 하였음에도 불구하고 에러가 발생하였기에 서치를 해보았다. 
- 가장 많이 나오는 것은 다음과 같았다.
  1. settings.py의 INSTALLED_APPS에 'rest_framework'를 등록하지 않았다. (해당 X)
  2. drf를 install 하지 않았다. (해당 X)
- 에러 해결의 어려운 점 중 하나가 이런 것 같다. 같은 에러를 내뱉음에도 불구하고 원인은 정말 다양하다. 
  - 예시로, INSTALLED_APPS에 앱 등록 시 스펠링을 틀렸더라도 같은 에러를 내뱉을 것이다. 이를 계속 맞게 보고 몇 시간 며칠을 에러 해결에 힘쓴다고 생각하면 해결했을 때의 그 허탈함은 상상만 해도 정말 미칠 지경이다. 

#### Solution

- 도대체 무엇인 문제인고 하며 서치를 계속해보다 drf를 install 하고 설치가 잘 되었는지 확인하기 위해 터미널에 pip list 명령어를 입력하는 글을 보게 되었다. 

  - 그리고, drf install도 나와 살짝 달랐다.

    ```python
    pip install djangorestframework # 내가 입력한 명령어
    pip install django-rest-framework # 다른 사람 것
    ```

- 우선, pip list를 해보니 drf가 설치되어있지 않았다,,!(왜인지는 모름,, install 할 때 별다른 에러도 없었는데 안됐던 것이었나,,?)

- pip install django-rest-framework 명령어를 입력하고 pip list를 하니 그제서야 설치가 되어진 것을 확인할 수 있었다. 

#### 에러 해결,,!!
