## ModuleNotFoundError: No module named 'rest_framework_authtoken'

#### Issue

- 'dj-rset-auth' 라이브러리를 사용해 회원가입, 로그인, 로그아웃 기능을 구현하려고 하였다.

- settings.py, urls.py 설정 후 migrate 하려고 하니 다음과 같은 에러가 발생.

  ```markdown
  > ModuleNotFoundError: No module named 'rest_framework_authtoken'
  ```



#### Solution

- settings.py 의 INSTALLED_APPS 내에 라이브러리를 잘못 넣어주어서 생긴 오류였다.

  ```markdown
  - 처음에는 INSTALLED_APPS에 'rest_framework_authtoken' 이라고 넣었는데, 'rest_framework.authtoken'으로 바꾸어주니 해결이 되었다.
  
  - 나는 분명 여러 자료를 보고 'rest_framework_authtoken' 라고 한 것이었는데 그 사람들은 어떻게 한 거지,,?
  ```

  
