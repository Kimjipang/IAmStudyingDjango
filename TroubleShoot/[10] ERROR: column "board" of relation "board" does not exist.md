## ERROR: column "board" of relation "board" does not exist

#### Issue



- postgresql db를 사용하여 DB 테이블에 데이터를 Insert 도중 다음과 같은 에러가 나타났다.

  - 작성했던 쿼리문 : INSERT INTO board(boardId, title) VALUES (1, 'Docs')
  - 에러 문구

  ```markdown
  > ERROR: column "board" of relation "board" does not exist
  ```



#### Solution

- DB 종류마다 정해져 있는 각자의 규칙이 있다. PostgreSQL은 대소문자를 구분하지 않고 모든 쿼리문을 전부 소문자로 바꾸어 준다고 한다. 

- 필자는 'board' 테이블의 PK를 'boardId'로 지정하였기 때문에 대문자 'I'를 입력하려면 쌍따옴표("") 안에 컬럼 명을 입력해야 한다고 한다. 

  ```markdown
  INSERT INTO board("boardId", title) VALUES (1, 'IRON MAN')
  	-> 대소문자를 구분해야 할 곳을 쌍따옴표로 감싸주면 된다.
  ```



#### **에러 해결!!**
