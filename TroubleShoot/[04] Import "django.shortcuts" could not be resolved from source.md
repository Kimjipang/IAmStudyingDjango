## Import "django.shortcuts" could not be resolved from source

#### Issue

- 하루 전에 종료했던 VSC를 다시 구동하였는데, 아무런 에러가 발생하지 않았던 VSC에서 아래와 같은 에러가 발생하였다.

  ```markdown
  > "django.shortcuts" could no be resolved from source
  ```

#### Reason Why?

```markdown
> 서치를 한 결과, 인터프리터가 구축한 가상 환경이 아닌 Python으로 되어 있어 발생한 오류였다.
```

<img width="700" alt="스크린샷 2022-11-18 오후 1 21 51" src="https://user-images.githubusercontent.com/91196025/202952783-b96ce031-e675-420b-9634-b2fe7c209417.png">

#### Solution

```markdown
> 해결 방법은 interpreter를 구축해놓은 가상 환경으로 바꾸어주면 된다.
- cmd + shift + p
- Python : Select Interpreter(Python : 인터프리터 선택)
- 해당 인터프리터 선택(필자 기준 )
```

