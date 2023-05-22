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



