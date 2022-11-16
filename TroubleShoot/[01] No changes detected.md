## No changes detected

#### Issue

- Django의 MTV 패턴에서 Model을 생성하고 변경한 내용을 데이터베이스에 적용시키기 위해 makemigrations 및 migrate를 하고자 하였다.

- 이때, 아래와 같은 에러가 발생하였다.

  ```markdown
  > No changes detected
  ```

  - 해당 에러 solution에 대해서는 조금 이따 이야기하고, 먼저 makemigrations와 migrate가 무엇인지 살펴보겠다.

> makemigrations
>
> - 모델을 변경한 후, 변경한 내용을 기록하여 파일로 만들어주는 과정
>
>   ```python
>   python manage.py makemigrations
>   ```



> migrate
>
> - makemigrations를 통해 생성된 파일을 실제로 실행시켜 실제 데이터베이스에 변경 사항을 적용시켜주는 과정.
>
>   ```python
>   python manage.py migrate
>   ```
>
> 

**즉, migrate를 해야 최종적으로 데이터베이스에 데이터들이 생성, 삭제, 수정이 되는 것이다.**





#### Solution

- 이 에러를 해결하기 위해 정말 많은 시간이 소요되었다. 해당 에러인 "No changes detected"를 서치하면 동일한 솔루션이 굉장히 많았다. 

  1. 솔루션은 프로젝트 디렉토리의 settings.py 파일 내의 INSTALLED_APPS에 model을 변경한 app(필자 기준 board)을 넣어야 한다거나

  <img width="500" alt="스크린샷 2022-11-16 오후 5 11 49" src="https://user-images.githubusercontent.com/91196025/202142620-8235462b-b2c4-489a-81cb-79d7e5d42632.png">

  2. makemigrations 뒤에 app 이름을 붙여주는 것으로 에러를 해결했다고 했다.

  ```python
  python manage.py makemigrations board(필자 기준 app name)
  ```

- 필자는 이 에러를 찾는데에 엄청난 시간이 걸렸고 찾고 나서도 확실하게 확인하고자 다시 trouble을 만들고 테스트를 해보았다.

- 결과는 필자가 한 방법이 이 에러에 대한 solution은 아니었다. (멘붕,,)

- 이것 저것 테스트해 본 끝에 에러에 대한 확실한 solution을 찾을 수 있었다.

**solution은 간단했다. models.py 를 저장하면 되는 것이었다,,**

​									**해결!**

<img width="400" alt="스크린샷 2022-11-16 오후 6 26 51" src="https://user-images.githubusercontent.com/91196025/202143221-98cd808b-fc0e-403b-8333-ba221da6418a.png">

