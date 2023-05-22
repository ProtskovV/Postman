Postman. HW_2

## http://162.55.220.72:5005/first ## 
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
  pm.response.to.have.status(200);
});
```
3. Проверить, что в body приходит правильный string.
```
pm.test("Body matches string", function () {
    pm.expect(pm.response.text()).to.include("This is the first responce from server!ss");
});
```
![first](https://github.com/ProtskovV/Postman/assets/130400251/df086fef-fb0d-4341-b629-d97da3d34cbe)

## http://162.55.220.72:5005/user_info_3 ##
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
  pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var resp = pm.response.json();
```
4. Проверить, что name в ответе равно name s request (name вбить руками.)
```
pm.test("Name test resp", function () {
    pm.expect(resp.name).to.eql("vlad");
});
```
5. Проверить, что age в ответе равно age s request (age вбить руками.)
```
pm.test("Age test resp", function () {
    pm.expect(resp.age).to.eql("22");
});
```
6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```
pm.test("Salary test resp", function () {
    pm.expect(resp.salary).to.eql(300);
});
```
7. Спарсить request.
```
var req = request.data;
```
8. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Name test req", function () {
    pm.expect(resp.name).to.eql(req.name);
});
```
9. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Age test req", function () {
    pm.expect(resp.age).to.eql(req.age);
});
```
10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Salary test req", function () {
    pm.expect(+resp.salary).to.eql(+req.salary);
});
```
11. Вывести в консоль параметр family из response.
```
console.log(resp.family)
```
12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```
pm.test("Test u_salary_1_5_yaer", function () {
    pm.expect(resp.family.u_salary_1_5_year).to.eql(req.salary*4);
});
```
![info_3](https://github.com/ProtskovV/Postman/assets/130400251/e32398dc-29ef-485d-a034-c48a5ea034bc)

## http://162.55.220.72:5005/object_info_3 ##
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var resp = pm.response.json();
```
4. Спарсить request.
```
var req = pm.request.url.query.toObject ();
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Name test req", function () {
    pm.expect(+resp.name).to.eql(+req.name);
});
```
6. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Age test req", function () {
    pm.expect(resp.age).to.eql(req.age);
});
```
7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Salary test req", function () {
    pm.expect(+resp.salary).to.eql(+req.salary);
});
```
8. Вывести в консоль параметр family из response.
```
console.log(resp.family)
```
9. Проверить, что у параметра dog есть параметры name.
```
pm.test("Dog have name", function () {
    pm.expect(resp.family.pets.dog).to.property("name");
});
```
10. Проверить, что у параметра dog есть параметры age.
```
pm.test("Dog have age", function () {
    pm.expect(resp.family.pets.dog).to.property("age");
});
```
11. Проверить, что параметр name имеет значение Luky.
```
pm.test("Name = Luky", function () {
    pm.expect(resp.family.pets.dog.name).to.eql("Luky");
});
```
12. Проверить, что параметр age имеет значение 4.
```
pm.test("Age = 4", function () {
    pm.expect(resp.family.pets.dog.age).to.eql(4);
});
```
![image](https://github.com/ProtskovV/Postman/assets/130400251/24389882-c8c5-4190-a6b2-772d94aa6687)

## http://162.55.220.72:5005/object_info_4 ##

1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var resp = pm.response.json();
```
4. Спарсить request.
```
var req = pm.request.url.query.toObject ();
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Name test req", function () {
    pm.expect(+resp.name).to.eql(+req.name);
});
```
6. Проверить, что age в ответе равно age из request (age забрать из request.)
```
pm.test("Age test req", function () {
    pm.expect(+resp.age).to.eql(+req.age);
});
```
7. Вывести в консоль параметр salary из request.
```
console.log(req.salary)
```
8. Вывести в консоль параметр salary из response.
```
console.log(resp.salary)
```
9. Вывести в консоль 0-й элемент параметра salary из response.
```
console.log(resp.salary[0])
```
10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```
console.log(resp.salary[1])
```
11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```
console.log(resp.salary[2])
```
12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```
pm.test("Salary test req [0]", function () {
    pm.expect(+resp.salary[0]).to.eql(+req.salary);
});
```
13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```
pm.test("Salary test req [1]", function () {
    pm.expect(+resp.salary[1]).to.eql(+req.salary*2);
});
```
14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```
pm.test("Salary test req [2]", function () {
    pm.expect(+resp.salary[2]).to.eql(+req.salary*3);
});
```
15. Создать в окружении переменную name
16. Создать в окружении переменную age
17. Создать в окружении переменную salary
18. Передать в окружение переменную name
```
pm.environment.set("name", "vlad")
```
19. Передать в окружение переменную age
```
pm.environment.set("age", 22)
```
20. Передать в окружение переменную salary
```
pm.environment.set("salary", 300)
```
21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```
for(var i = 0; i < 3; i++ ){
	console.log(resp.salary[i])
}
```
![info_4](https://github.com/ProtskovV/Postman/assets/130400251/56daa1d3-8471-4dfa-83c5-3acc32143f22)

## http://162.55.220.72:5005/user_info_2 ##
1. Вставить параметр salary из окружения в request
2. Вставить параметр age из окружения в age
3. Вставить параметр name из окружения в name
4. Отправить запрос.
![image](https://github.com/ProtskovV/Postman/assets/130400251/9d8da6a5-0cc5-4321-bf84-624ac5d4b548)

5. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
6. Спарсить response body в json.
```
var resp = pm.response.json();
```
7. Спарсить request.
```
var req = request.data;
```
8. Проверить, что json response имеет параметр start_qa_salary
```
pm.test("Test start_qa_salary", function () {
    pm.expect(resp).to.property("start_qa_salary");
});
```
9. Проверить, что json response имеет параметр qa_salary_after_6_months
```
pm.test("Test qa_salary_after_6_months", function () {
    pm.expect(resp).to.property("qa_salary_after_6_months");
});
```
10. Проверить, что json response имеет параметр qa_salary_after_12_months
```
pm.test("Test qa_salary_after_12_months", function () {
    pm.expect(resp).to.property("qa_salary_after_12_months");
});
```
11. Проверить, что json response имеет параметр qa_salary_after_1.5_year
```
pm.test("Test qa_salary_after_1.5_year", function () {
    pm.expect(resp).to.property("qa_salary_after_1.5_year");
});
```
12. Проверить, что json response имеет параметр qa_salary_after_3.5_years
```
pm.test("Test qa_salary_after_3.5_years", function () {
    pm.expect(resp).to.property("qa_salary_after_3.5_years");
});
```
13. Проверить, что json response имеет параметр person
```
pm.test("Test person", function () {
    pm.expect(resp).to.property("person");
});
```
14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
```
pm.test("Test start_qa_salary req", function () {
    pm.expect(+resp.start_qa_salary).to.eql(+req.salary);
});
```
15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
```
pm.test("Test qa_salary_after_6_months req", function () {
    pm.expect(+resp.qa_salary_after_6_months).to.eql(+req.salary*2);
});
```
16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
```
pm.test("Test qa_salary_after_12_months req", function () {
    pm.expect(+resp.qa_salary_after_12_months).to.eql(+req.salary*2.7);
});
```
17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
```
pm.test("Test qa_salary_after_1.5_year req", function () {
    var sal_1_5_y = resp ["qa_salary_after_1.5_year"];
    pm.expect(sal_1_5_y).to.eql(+req.salary*3.3);
});
```
18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
```
pm.test("Test qa_salary_after_3.5_years req", function () {
    var sal_3_5_y = resp ["qa_salary_after_3.5_years"];
    pm.expect(sal_3_5_y).to.eql(+req.salary*3.8);
});
```
19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
```
pm.test("Test u_name[1]", function () {
    pm.expect(+resp.person.u_name[1]).to.eql(+req.salary);
});
```
20. Проверить, что что параметр u_age равен age из request (age забрать из request.)
```
pm.test("Test u_age", function () {
    pm.expect(+resp.person.u_age).to.eql(+req.age);
});
```
21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
```
pm.test("Test u_salaru_5_years req", function () {
    pm.expect(+resp.person.u_salary_5_years).to.eql(+req.salary*4.2);
});
```
22. * Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
```
for(var i = 0; i < 3; i++){
console.log(Object.entries(resp.person)[i]);
}
```
