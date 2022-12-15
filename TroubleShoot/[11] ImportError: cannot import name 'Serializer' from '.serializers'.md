## ImportError: cannot import name 'WorkspaceSerializer' from 'workspace.serializers'



#### Issue

- DRF를 활용하여 restAPI를 작성하고 테스트를 위해 runserver를 했더니 다음과 같은 에러가 나타났다.

  ```markdown
  > ImportError: cannot import name 'WorkspaceSerializer' from 'workspace.serializers'
  ```



#### Solution

- workspace라는 app 내에 작성한 serializers.py 코드를 들여다 보았다. 결과적으로 에러의 원인은 import 방식이 잘못 되어서였다.

- 여태 크게 신경 쓰지 않았던 부분 중 하나인데 같은 앱 내의 다른 파일을 import 할 때에 필자는 아래와 같이 작성했었다.

  ```markdown
  from models import Workspace
  	-> 현재 앱 내의 models.py에 작성된 Workspace를 import하는 것.
  ```

- 하지만, 이렇게 하니 현재 앱의 models로부터 import를 하려는 것인지를 인식하지 못하는 문제가 발생한 것이었다. 

- 제대로 된 import를 하기 위해서는 아래와 같이 하면 된다.

  ```markdown
  from .models import Workspace
  	-> 정상적으로 import를 한다.
  ```

#### 

#### **에러 해결!!**

