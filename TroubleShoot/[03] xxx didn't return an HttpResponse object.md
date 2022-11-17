## ValueError: The view photo.views.photo_post didn't return an HttpResponse object. It returned None instead.



#### Issue

- views.py 파일을 작성한 후, render() 메서드로 사용자가 볼 수 있는 화면을 반환하려 했다. 

- 이때, 아래와 같은 에러가 발생하였다.

  ```markdown
  > ValueError: The view photo.views.photo_post didn't return an HttpResponse object. It returned None instead.
  ```



#### Solution 

```markdown
> 에러에 대해 서치했을 때 나오는 solution들이 나의 문제와는 달랐다.
결론부터 이야기하면 나의 문제는 들여쓰기 문제였다. 

but, 해당 에러에 대해 서치를 하게 되면 나오는 solution은 이러했다.
원하는 결과를 사용자들이 볼 수 있게 하기 위해서는 렌더링(render())을 거쳐야 하는데, views.py 파일은 무조건적으로 render()를 return 해야 하는 것. 단순히 render() 메서드를 호출하는 것으로는 안된다고 한다. 

		-> 결론 : views.py는 render() 호출이 아닌 필히 render()를 							return 해야 한다.
```

