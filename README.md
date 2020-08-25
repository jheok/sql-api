# python에서 mysql, mariaDB의 접속

Python에서 Mysql 또는  MariaDB  접속해서 정보를 가져오는 방법

Python에서는 PyMySQL 모듈과 MySQLDB 모둘 두 가지 형태로 접속 할 수 있다.

1. <필수> connect( )
2. <필수> cursor( )
3. <옵션> execute( )
4. <옵션> fetchalll( ), fetchall( ), description( )
5. <필수> close( )

- pymysql 모듈을 이용한 mysql 접속법

```python
import urllib
import pymysql
from urllib.request import urlopen
from bs4 import BeautifulSoup

# Open database connection
conn = pymysql.connect(host='localhost', port=3306, user='root', passwd='maria', db='estdb',charset='utf8',autocommit=True)

# prepare a cursor object using cursor() method
cursor = conn.cursor()

# execute SQL query using execute() method.
cursor.execute("SELECT * FROM kakao")

# Fetch a single row using fetchone() method.
data = cursor.fetchone()

print ("Database version : %s " % data)

# disconnect from server
conn.close()
```

