## Couldn't import Django. Are you sure it's installed and available on your PYTHONPATH environment variable? Did you forget to activate a virtual environment?



#### Issue

- 문제 없이 잘 구동되던 프로젝트가 run이 되지 않고, 아래 2개의 명령어에서 다음과 같은 에러가 나타났다.
  1. python manage.py startapp [appname]
  2. python manage.py runserver 

```markdown
> Couldn't import Django. Are you sure it's installed and available on your PYTHONPATH environment variable? Did you forget to activate a virtual environment?
```

- 우선 굉장히 당황스러웠다. 잘 되던 것이 되지 않는다는 것과 에러에 대한 설명 때문이었다.
- 장고를 import 할 수 없고 가상 환경을 설치를 했는지와 활성화를 했는지에 대한 에러였는데, 애초에 잘 되었던 것이었기 때문에 모두 해당이 되지 않는다 생각했다.

#### Solution

- 에러에 대한 설명에 맞게 장고를 다시 설치해보기도 하고, 가상 환경을 재활성화 시켜보기도 하였다. python interpreter가 제대로 설정이 되어 있는지도,,,
- 아무것도 되지 않았고, 구글에 서치를 해보기 시작했다. 

```markdown
1. 가상 환경에 django가 설치되어 있지 않기 때문
2. 환경변수에 python이 설치된 경로가 잘못 되어 있어 python을 인식하지 못하기 때문
- 이 밖에도 에러에 대한 몇 가지 해결책들이 있었지만 먹히지 않았다.
- 그러던 중 stack overflow에서 한 해결법을 보았고, 이에 대한 것은 다음과 같았다.
		- If you are working on a machine where it doesn't have permissions to all the files and moreover you have two versions such as defaulf 2.7 & latest 3.6 then while running the command use the python version with the command. 
		- 완벽한 해석은 아니지만 여러 버전의 파이썬이 설치된 경우에는 python명령		어를 사용시 버전을 명시해주어야 한다는 것.
		
- python3 manage.py startapp [appname]
- python3 manage.py runserver

	> 해결! 정상 작동된다.
```

