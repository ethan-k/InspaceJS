# 파이썬 ORM sqlalchemy 사용법

파이썬 설치

현재 파이썬 스크리븥 파이썬 버전: 2.7
[아나콘다 파이썬 다운및 설치](https://www.continuum.io/downloads)


ORM 라이브러리: sqlalchemy [공식 Document](http://docs.sqlalchemy.org/en/rel_1_1/)

기본으로 MYSQL과 연결할수 있는 드라이버가 설치되어있어야 한다.
여러 드라이버중에 pymysql을 설치

    $ pip install pymysql


```python 
import sqlalchemy
```

ORM을 사용방법

### 1. 사용 준비하기

engine: 데이터베이스에 연결하는 엔진을 연결한다.

```python
from sqlalchemy import create_engine

''' SQLLITE 사용시 '''
engine = create_engine('sqlite:///:memory:', echo=True)

''' MYSQL 사용시 '''

```

맵핑 선언
ORM을 사용하기 위해서는 파이썬과 데이터베이스에서 연결해주는 작업이 필요한데
아래 Base가 그와 같은 기능을 실현수
```python
from sqlalchemy.ext.declarative import declarative_base
Base = declarative_base()
```

### 2. 테이블 선언하기 

```python
from sqlalchemy import Column, Integer, String
class User(Base):
    __tablename__ = 'users'
    id = Column(Integer, primary_key=True)
    name = Column(String)
    fullname = Column(String)
    password = Column(String)
    def __repr__(self):
       return "<User(name='%s', fullname='%s', password='%s')>" % (
                            self.name, self.fullname, self.password)

```

### 3. 데이터 베이스 실제로 테이블 만들기
이 작업을 통해서 Base 를 상속받은 클래스의 테이블들이 데이터베이스에 생성된다.

``` python
Base.metadata.create_all(engine)
```








