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
![EP_2_5](https://github.com/artemlat/postman_hw_3/blob/main/EP_2(5).png)
![EP_2_6](https://github.com/artemlat/postman_hw_3/blob/main/EP_2(6).png)
![EP_2_7](https://github.com/artemlat/postman_hw_3/blob/main/EP_2(7).png)
![EP_2_8](https://github.com/artemlat/postman_hw_3/blob/main/EP_2(8).png)
![EP_2_9](https://github.com/artemlat/postman_hw_3/blob/main/EP_2(9).png)

### EP_2 (/get_test_user)

![EP_2_10](https://github.com/artemlat/postman_hw_3/blob/main/EP_2_10.png)
![EP_2_11](https://github.com/artemlat/postman_hw_3/blob/main/EP_2(11).png)

### EP_3 (/new_data)

```
3) http://162.55.220.72:5005/new_data
req.
POST
age: int
salary: int
name: str
auth_token

Resp.
{'name':name,
  'age': int(age),
  'salary': [salary, str(salary*2), str(salary*3)]}

Тесты:
1) Статус код 200
2) Проверка структуры json в ответе.
3) В ответе указаны коэффициенты умножения salary, напишите тесты по проверке правильности результата перемножения на коэффициент.
4) проверить, что 2-й элемент массива salary больше 1-го и 0-го
```

![EP_3_1](https://github.com/artemlat/postman_hw_3/blob/main/EP_3(1).png)
![EP_3_2](https://github.com/artemlat/postman_hw_3/blob/main/EP_3(2).png)
![EP_3_3](https://github.com/artemlat/postman_hw_3/blob/main/EP_3(3_3).png)
![EP_3_4](https://github.com/artemlat/postman_hw_3/blob/main/EP_3(4).png)
![EP_3_5](https://github.com/artemlat/postman_hw_3/blob/main/EP_3(5).png)
![EP_3_6](https://github.com/artemlat/postman_hw_3/blob/main/EP_3(6).png)
![EP_3_7](https://github.com/artemlat/postman_hw_3/blob/main/EP_3(7).png)

### EP_4 (/test_pet_info)

```
4) http://162.55.220.72:5005/test_pet_info
req.
POST
age: int
weight: int
name: str
auth_token


Resp.
{'name': name,
 'age': age,
 'daily_food':weight * 0.012,
 'daily_sleep': weight * 2.5}


Тесты:
1) Статус код 200
2) Проверка структуры json в ответе.
3) В ответе указаны коэффициенты умножения weight, напишите тесты по проверке правильности результата перемножения на коэффициент.
```
![EP_4_1](https://github.com/artemlat/postman_hw_3/blob/main/EP_4(1).png)
![EP_4_2](https://github.com/artemlat/postman_hw_3/blob/main/EP_4(2).png)
![EP_4_3](https://github.com/artemlat/postman_hw_3/blob/main/EP_4(3).png)
![EP_4_4](https://github.com/artemlat/postman_hw_3/blob/main/EP_4(4).png)
![EP_4_6](https://github.com/artemlat/postman_hw_3/blob/main/EP_4(6).png)
![EP_4_7](https://github.com/artemlat/postman_hw_3/blob/main/EP_4(7).png)

### EP_5 (/get_test_user)

```
5) http://162.55.220.72:5005/get_test_user
req.
POST
age: int
salary: int
name: str
auth_token

Resp.
{'name': name,
 'age':age,
 'salary': salary,
 'family':{'children':[['Alex', 24],['Kate', 12]],
 'u_salary_1.5_year': salary * 4}
  }

Тесты:
1) Статус код 200
2) Проверка структуры json в ответе.
3) Проверить что занчение поля name = значению переменной name из окружения
4) Проверить что занчение поля age в ответе соответсвует отправленному в запросе значению поля age
```

![EP_5_1](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(1).png)
![EP_5_2](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(2).png)
![EP_5_3](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(3).png)
![EP_5_4](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(4).png)
![EP_5_5](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(5).png)
![EP_5_6](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(6_6).png)
![EP_5_7](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(7).png)
![EP_5_9](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(9).png)
![EP_5_10](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(10).png)
![EP_5_11](https://github.com/artemlat/postman_hw_3/blob/main/EP_5(11).png)

### EP_6 (/currency)

```
6) http://162.55.220.72:5005/currency
req.
POST
auth_token

Resp. Передаётся список массив объектов.
[
{"Cur_Abbreviation": str,
 "Cur_ID": int,
 "Cur_Name": str
}
…
{"Cur_Abbreviation": str,
 "Cur_ID": int,
 "Cur_Name": str
}
]

Тесты:
1) Можете взять любой объект из присланного списка, используйте js random.
В объекте возьмите Cur_ID и передать через окружение в следующий запрос.
```
![EP_6_1](https://github.com/artemlat/postman_hw_3/blob/main/EP_6(1).png)
![EP_6_2](https://github.com/artemlat/postman_hw_3/blob/main/EP_6(2).png)
![EP_6_3](https://github.com/artemlat/postman_hw_3/blob/main/EP_6(3).png)
![EP_6_4](https://github.com/artemlat/postman_hw_3/blob/main/EP_6(4).png)

### EP_7 (/curr_byn)

```
7) http://162.55.220.72:5005/curr_byn
req.
POST
auth_token
curr_code: int

Resp.
{
    "Cur_Abbreviation": str
    "Cur_ID": int,
    "Cur_Name": str,
    "Cur_OfficialRate": float,
    "Cur_Scale": int,
    "Date": str
}

Тесты:
1) Статус код 200
2) Проверка структуры json в ответе.
```
![EP_7_1](https://github.com/artemlat/postman_hw_3/blob/main/EP_7(1).png)
![EP_7_2]()
