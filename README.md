# #3. Postman  
*Here I continued to learn how to create requests, use autotests, use functions and cycles in Postman.*  

### EP_1 (/login)  

```
1) необходимо залогиниться
POST
http://162.55.220.72:5005/login
login : str (кроме /)
password : str

Приходящий токен необходимо передать во все остальные запросы.
```
![EP_1_1](https://github.com/artemlat/postman_hw_3/blob/main/EP_1_1.png)
![EP_1](https://github.com/artemlat/postman_hw_3/blob/main/EP_1.png)

### EP_2 (/user_info)

```
2) http://162.55.220.72:5005/user_info
req. (RAW JSON)
POST
age: int
salary: int
name: str
auth_token


resp.
{'start_qa_salary':salary,
 'qa_salary_after_6_months': salary * 2,
 'qa_salary_after_12_months': salary * 2.9,
 'person': {'u_name':[user_name, salary, age],
                                'u_age':age,
                                'u_salary_1.5_year': salary * 4}
                                }

Тесты:
1) Статус код 200
2) Проверка структуры json в ответе.
3) В ответе указаны коэффициенты умножения salary, напишите тесты по проверке правильности результата перемножения на коэффициент.
4) Достать значение из поля 'u_salary_1.5_year' и передать в поле salary запроса http://162.55.220.72:5005/get_test_user
```
![EP_2_1](https://github.com/artemlat/postman_hw_3/blob/main/EP_2_1.png)
![EP_2_2](https://github.com/artemlat/postman_hw_3/blob/main/EP_2(2).png)
![EP_2_3](https://github.com/artemlat/postman_hw_3/blob/main/EP_2(3).png)
![EP_2_4](https://github.com/artemlat/postman_hw_3/blob/main/EP_2(4).png)
![EP_2_5]()


