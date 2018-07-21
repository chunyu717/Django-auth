# django-auth-practice

課程 
https://www.udemy.com/build-a-user-authentication-web-app-with-python-and-django/learn/v4/overview

安裝 pythone 3.7

進入 django 工作資料夾
cd .\django-project\   

安裝虛擬環境
pip install virtualenv

建立虛擬環境
Set-ExecutionPolicy Unrestricted
virutalenv .

啟動虛擬環境
.\Scripts\activate

虛擬環境內 安裝 django
pip install django

建立專案 my_site 
mkdir my_site
cd .\my_site\
django-admin.py startproject mysite .

啟動 server 
python .\manage.py runserver

db migrate
python .\manage.py migrate			

建立一個admin 的 user
python .\manage.py createsuperuser		

建立 app : authenticate
python .\manage.py startapp authenticate	


建立資料夾templates放 app 的所有 網頁  
 ~\my_site\authenticate\templates\    

建立資料夾templates\authenticate 放 app 的 authenticate 網頁  
 ~\my_site\authenticate\templates\authenticate\ 	  


無法透過 vscode 安裝 pylint 
所以在命令列裡面 pip install pylint
一般開啟 vscode  pylint 會報錯
然後 #code


view.py 是定義 view  接收到 reqeust 後處理的行為 ， 行為處理後最後通常是 render 到 html 或是 redirect到 html
urls.py 註冊 view fucntin 的 url path . 


是用手刻的 login , logout
但是 register 用所謂的 automatic 方法
from django.contrib.auth.forms import UserCreationForm

講師不太喜歡覺得挺複雜的 ref. 
https://docs.djangoproject.com/en/2.0/ref/forms/fields/
https://docs.djangoproject.com/en/2.0/ref/forms/widgets/


但是 automatic  把所有 form validation 都做完了
只要遵循方法她就會用正確的方式把 register 跟 edit user 做好。


form.py 是做原本 django 提供 form 的客製化動作(overlap)
