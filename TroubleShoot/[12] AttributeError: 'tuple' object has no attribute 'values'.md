## AttributeError: 'tuple' object has no attribute 'values'

#### Issue

- 백엔드 API 코드를 짜다가 테스트를 위해 작성한 url에 접속하여 post를 날려보았는데 다음과 같은 에러가 나타났다.

  ```markdown
  > AttributeError: 'tuple' object has no attribute 'values'
  ```

#### Solution

- get동작은 정상적으로 되었기 때문에 처음에는 post 작업을 수행하는 코드에 문제가 있는지를 찾아보았다. 

- 해당 사항은 원인이 아니었고 다시 처음부터 찾아보기 시작하였다.

- 객체가 'values' 속성을 가지고 있지 않다는 말이 무슨 말인지에 대해 계속 고민을 거듭하다 답을 찾아내었다.

- API를 이용해 프론트엔드와 데이터를 주고 받을 때 json 형식으로 변환하게 되는데 장고에서는 이를 Serializer가 해주고 있다. 근데 serializers.py의 코드가 잘못되어 클라이언트로부터 온 request를 받아올 수가 없었던 것이었다. 

  ```markdown
  class ProjectSerializer(ModelSerializer):
      model = Project
      fields = ('pid', 'workspace', 'name', 'status')
  
  ```

  ```markdown
  class ProjectSerializer(ModelSerializer):
      class Meta:
          model = Project
          fields = ('pid', 'workspace', 'name', 'status')
  ```

  

#### 에러 해결!!

