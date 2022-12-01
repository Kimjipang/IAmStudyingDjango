## ?: (urls.W005) URL namespace 'admin' isn't unique. You may not be able to reverse all URLs in this namespace



#### Issue

- Django에서 제공하는 User Model을 커스터마이징하는 것을 테스트하다 다음과 같은 에러가 나타났다.

  ```markdown
  > ?: (urls.W005) URL namespace 'admin' isn't unique. You may not be able to reverse all URLs in this namespace
  ```



#### Solution

- admin이 유일하지 않다는 것인데,, 뭐지하고 바로 서치를 했다.
- 원인은 관리자 페이지로 연결되는 'admin/' url이 프로젝트/urls.py와 앱/urls.py에 총 두 번 선언이 되어 있어서였다.



#### **에러 해결!!**

