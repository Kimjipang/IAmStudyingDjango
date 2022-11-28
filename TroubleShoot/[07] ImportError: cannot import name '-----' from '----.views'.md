
## ImportError: cannot import name '-----' from '----.views'

#### Issue

- DRF의 view를 CBV 방식으로 작성하며 serializer를 사용하다 중복되는 serializer 코드를 줄이기 위해 mixins를 사용했다.
- views.py에서 api를 작성 후, urls.py에서 url을 view와 연결하는 것까지 마치고 runserver를 하니 아래와 같은 에러가 나타났다.

```markdown
> ImportError: cannot import name '-----' from '----.views'
```

#### Solution

- 에러는 간단했다. mixins를 사용하기 위해 기존에 있던 CBV로 작성된 코드를 주석 처리했기 때문에 urls.py에서 import할 것을 찾지 못했기 때문. 
- urls.py에 연결시킨 view의 path & import한 클래스명을 제거 혹은 주석처리하면 에러는 해결된다.


#### 에러 해결!
