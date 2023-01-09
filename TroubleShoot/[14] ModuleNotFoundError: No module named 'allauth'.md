
## ModuleNotFoundError: No module named 'allauth'

#### Issue

- 'dj-rest-auth' 라이브러리를 사용하기 위해 필요한 것들을 구현하고 migrate를 하면 다음과 같은 에러를 볼 수 있다. 

  ```markdown
  > ModuleNotFoundError: No module named 'allauth'
  ```

- allauth를 찾을 수 없다는데,, 난 allauth를 하려고 한 적도 없는데용? 

- dj-rest-auth 라이브러리를 pip install 했더니 위처럼 에러가 나온 것이었다. 

#### Solution

- dj-rest-auth 라이브러리를 pip install 했더니 위처럼 에러가 나온 것이었다. 

- 물론 이유는 아직도 모르겠다,,! 그저,, rest-auth-token을 사용하려면 allauth 라이브러리가 필요한가보다~~ 라고 생각 중이다 'ㅅ'

- 각설하고! 해결방법은 다음과 같다.

  ```markdown
  1. pip install django-allauth 로 allauth 설치
  2. INSTALLED_APPS에 'allauth' 추가하면 끝
  ```

#### 에러 해결!!

#### < 마무리 >

- 장고를 해보면서 ModuleNotFoundError는 꽤나 자주 만나는 에러 중 하나이다. 이를 보통 구글링 하면 INSTALLED_APPS에 앱 혹은 라이브러리를 추가하지 않지 않았냐는 답변이 많다.
- 아직 엄청난 초보이지만, 여태 경험한 바로는 그러한 경우는 왠만하면 없었던 거 같다.(필자 기준 INSTALLED_APPS를 추가하지 않은 경우는 진짜 극 초반을 제외하고는 없었기 때문,,!)
- 항상 무엇인가 다른 원인이었다. 이것들도 하다보면 나중에는 에러를 바로 해결할 수 있겠지만, 그전까지는 열심히 기록을 해야겠다.
