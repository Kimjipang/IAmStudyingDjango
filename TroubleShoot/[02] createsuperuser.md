
#### Issue[sqlite3.OperationalError: no such table: auth_user]

- VSC에서 Django 프로젝트를 생성 후, Django에서 기본적으로 제공하는 admin 페이지의 admin 계정을 만들려 했다.

  <img width="1220" alt="스크린샷 2022-11-16 오후 3 47 13" src="https://user-images.githubusercontent.com/91196025/202110317-56dd7150-e3d4-42ad-b59b-fd23c0183dca.png">

- 이때, 아래와 같은 에러가 발생하였다.

```markdown
> sqlite3.OperationalError: no such table:auth_user
```

<img width="444" alt="스크린샷 2022-11-16 오후 3 47 33" src="https://user-images.githubusercontent.com/91196025/202110347-6dc6265f-5d10-4669-959b-efa8da5e7763.png">

#### Solution

auth_user 테이블이 없어서 발생하는 에러 즉, createsuperuser(superuser create)를 할 테이블(DB)이 존재하지 않아 생기는 에러였다.

테이블을 만들어 주면 해결되는데, 테이블을 만들기 위해서는 migrations 해주어야 함.

```markdown
> python manage.py migrate
		-> 데이터베이스에 변경 사항을 적용시켜주는 코드
```

​														해결!

<img width="266" alt="스크린샷 2022-11-16 오후 4 06 44" src="https://user-images.githubusercontent.com/91196025/202110378-60bfa959-ba04-4080-bb30-47de89c7292b.png">

