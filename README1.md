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

