# 透過以下步驟 可以建立 Django 的 Restful api 服務， 專案說明 : 
https://www.udemy.com/build-a-user-authentication-web-app-with-python-and-django/learn/v4/overview
此專案有 包含 template html 網頁的部分。實作 Loing In Page 登入的操作
其中 authenticate, login, logout, update_session_auth_hash 使用到的都是 Django 內建的涵式.  Django 強大的框架提供了很多實作的方法. 

Step : 
安裝 pythone 3.7

進入 django 工作資料夾
$ cd .\django-project\   

安裝虛擬環境
$ pip install virtualenv

建立虛擬環境
$ Set-ExecutionPolicy Unrestricted
$ virutalenv .

啟動虛擬環境
.\Scripts\activate

虛擬環境內 安裝 django
$ pip install django

建立專案 "my_site"
$ mkdir my_site
$ cd .\my_site\
$ django-admin.py startproject mysite .

啟動 server 
$ python .\manage.py runserver

db migrate
$ python .\manage.py migrate			

建立一個 admin 的 user
$ python .\manage.py createsuperuser		

建立 app : authenticate
$ python .\manage.py startapp authenticate	

建立資料夾templates放 app 的所有 網頁  
 ~\my_site\authenticate\templates\    

建立資料夾templates\authenticate 放 app 的 authenticate 網頁  
 $ ls ~\my_site\authenticate\templates\authenticate\ 	 
 ```
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       2020/7/2  下午 03:03           3319 base.html
-a----       2020/7/2  下午 03:03            894 change_password.html
-a----       2020/7/2  下午 03:03           1003 edit_profile.html
-a----       2020/7/2  下午 03:03            335 home.html
-a----       2020/7/2  下午 03:03            599 login.html
-a----       2020/7/2  下午 03:03            923 register.html
 ```
 
無法透過 vscode 安裝 pylint (因為是在虛擬環境內 ) 所以在命令列裡面 $ pip install pylint
正常程序開啟 vscode pylint 會報錯  要用 console 執行  $ code

urls.py 註冊 view fucntin 的 url path . 

view.py 是定義 view  接收到 reqeust 後處理的行為 ， 行為處理後最後通常是 render 到 html 或是 redirect到 html,  當中 register, edit_profile 用所謂的 automatic 方法 使用 Django 內建的 UserCreationForm & UserChangeForm 
from django.contrib.auth.forms import UserCreationForm, UserChangeForm
automatic 會把所有 form validation 都做完了。只要遵循方法她就會用正確的方式把 register 跟 edit user 做好。

form.py  作者透過 form.py overlap(overwrite)做原本 django 提供 form 的客製化動作
