### sqlite3.OperationalError: no such table: auth_user

#### Issue

- VSC에서 Django 프로젝트를 생성 후, Django에서 기본적으로 제공하는 admin 페이지의 admin 계정을 만들려 했다.

  <img src="/Users/keemjihwan/Desktop/스크린샷 2022-11-16 오후 3.47.13.png" alt="스크린샷 2022-11-16 오후 3.47.13" style="zoom: 100%;" />

- 이때, 아래와 같은 에러가 발생하였다.

```markdown
> sqlite3.OperationalError: no such table:auth_user
```

![스크린샷 2022-11-16 오후 3.47.33](/Users/keemjihwan/Desktop/스크린샷 2022-11-16 오후 3.47.33.png)

#### Solution

auth_user 테이블이 없어서 발생하는 에러 즉, createsuperuser(superuser create)를 할 테이블(DB)이 존재하지 않아 생기는 에러였다.

테이블을 만들어 주면 해결되는데, 테이블을 만들기 위해서는 migrations 해주어야 함.

```markdown
> python manage.py migrate
		-> 데이터베이스에 변경 사항을 적용시켜주는 코드
```

​														해결!

<img src="/Users/keemjihwan/Desktop/Typora/[00] Screen Shot/스크린샷 2022-11-16 오후 4.06.44.png" alt="스크린샷 2022-11-16 오후 4.06.44" style="zoom:67%;" />

