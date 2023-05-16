Postman. HW_2

http://162.55.220.72:5005/first
1. Отправить запрос.
2. Статус код 200
```
*pm.test("Status code is 200", function () {*
  *pm.response.to.have.status(200);*
*});*
```
3. Проверить, что в body приходит правильный string.
```
pm.test("Body matches string", function () {
    pm.expect(pm.response.text()).to.include("This is the first responce from server!ss");
});
```
![first](https://github.com/ProtskovV/Postman/assets/130400251/df086fef-fb0d-4341-b629-d97da3d34cbe)
user_info_3

