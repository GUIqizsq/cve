SQL injection vulnerability exists in ibos oa v4.5.5

official website:http://www.ibos.com.cn/

version:4.5.5

Function point: Integrated Office = "Information Bulletin =" Delete category

![WPS图片(1)](https://github.com/GUIqizsq/cve/assets/139303407/0c3358b0-4f3f-48e9-9197-8772b4a86c1e)
![WPS图片(2)](https://github.com/GUIqizsq/cve/assets/139303407/447fd4f9-ae04-431f-965c-74ff564e1416)

POC

Route: r=article/category/del

Successfully burst the database name by reporting an error injection

![WPS图片(3)](https://github.com/GUIqizsq/cve/assets/139303407/cf8058d7-d280-45d2-8b29-f77b354fd09a)

analyze

The route found here calls the Delete method in modules

![WPS图片(4)](https://github.com/GUIqizsq/cve/assets/139303407/e586a3ca-4e07-4429-83ce-ff4c45cb98e6)

In this method, the passed catid parameter is carried to the fetchByPk() method under module to execute the SQL statement

![WPS图片(5)](https://github.com/GUIqizsq/cve/assets/139303407/447793e5-93ec-4afb-a6e7-52f80b39dfe6)

Cached data is not queried by findByPk()

![WPS图片(6)](https://github.com/GUIqizsq/cve/assets/139303407/13c7c3a8-4637-4fe8-ac1a-7c04158e8ea2)

Query() executes the SQL statement

![WPS图片(7)](https://github.com/GUIqizsq/cve/assets/139303407/3f2743ac-141e-4712-90d8-8090e755f3b4)
