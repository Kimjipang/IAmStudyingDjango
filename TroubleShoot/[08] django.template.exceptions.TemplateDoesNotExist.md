
## django.template.exceptions.TemplateDoesNotExist**

#### Issue

- DRF로 refresh token와 access token을 발급 받는 코드를 작성한 후 이를 테스트하기 위해 설정해놓은 url에 접속했을 때 다음과 같은 에러가 나타났다. 

```markdown
> django.template.exceptions.TemplateDoesNotExist
```



#### Solution

- Django 대신 DRF로 개발을 하는 이유는 백엔드 API를 설계하기 위해서인데, Template이 존재하지 않다는 에러가 의아했다. 분명 잘 되었었던 것 같은데,,
- 알고보니 settings.py의 INSTALLED_APPS에 rest_framework을 등록하지 않았던 것!
  - DRF로 api 설계를 했지만 정작 DRF를 쓰고 있지 않아 template을 필요로 했던 것이 이유였다. 

<img width="600" alt="스크린샷 2022-11-30 오후 1 44 48" src="https://user-images.githubusercontent.com/91196025/204710267-db2ed53a-e9a4-46db-a841-7ee5c21a7536.png">



#### **에러 해결!**
