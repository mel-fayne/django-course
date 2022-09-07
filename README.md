# Django Crash Course by Dennis Ivy

## 1. Project Setup

[Link](https://www.youtube.com/watch?v=xv_bwpA_aEA&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=1)

**Useful Commands**
1. django-admin : check if django is installed correctly
2. django-admin startproject <projectname> : create a django project
3. python3 manage.py runserver : run the project on Port 8000
4. python3 manage.py startapp <appname> : create an app in the project file
5. python manage.py createsuperuser : create an admin user
6. pip install django-cors-headers : install cors headers

**Basic Project File Structure**

1. manage.py - don't tocuh this file. Gives list of commands we'll use
2. wsgi.py - web serveer files
3. urls.py - a url routing system. we'll add a list of paths
4. settings.py - the main configurations to your django project

**Useful Commands & Steps**
1. python3 manage.py startproject crm - create the django project
2. python3 manage.py startapp accounts - create an application within the prject called accounts
3. Register the app in the project in settings.py

**Basic App File Structure**
Key Files
1. admin.py
2. models.py
3. views.py

## 2. URLs and Views

[Link](https://www.youtube.com/watch?v=QvTyqta3OJo&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=2)

![urls_views.png](../crm/static/images/urls_views.png)

**Setps done**
1. Create a urls.py file in accounts app
2. Create views functions in views.py 
3. Link views.py funcions to app urls.py 
4. Link app urls.py to projects.py

## 3. Templates & Inheritance

[Link](https://www.youtube.com/watch?v=9aEsZxaOwRs&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=3)

- Django specifically looks for : <br>
 --- app <br>
 -----templates <br>
 ------app <br>
 -------your html files <br>

!!!note
    Be sure to name the folder templates; that's what django looks for
- We build the templates/accounts files

## 4. Static Files & Images

[Link](https://www.youtube.com/watch?v=kqyfEz7TNI0&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=4)

- Note media urls and static urls in settings.py
- Also note statict folder and how we import static iles into html templates *{% load static %}

## 5. Database Models & Admin Panel

[Link](https://www.youtube.com/watch?v=mOu9fpfzyUg&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=5&t=491s)

- Created http://127.0.0.1:8000/admin/auth/user/
- Models :
  ![models.png](../crm/static/images/models.png)

- Worked on models.py
- python3 manage.py makemigrations &  python3 manage.py migrate - the command used to create  a model in models.py in the databse
- Remember to **register** your models in admin.py
  
## 6. Database Relationships | One To Many & Many to Many

[Link](https://www.youtube.com/watch?v=wIPHER2UBB4&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=6)

**One to Many Relationship**
- An Example : One Customer has placed 3 different orders
  
![one-to_many.png](../crm/static/images/one_to_many.png)

**Many to Many Relationship**
- An Example : A tag can have many products and a product can also have many tags.
  
![many_to_many.png](../crm/static/images/many_to_many.png)

- We added dummy data at this stage

## 7. Database Model Queries

[Link](https://www.youtube.com/watch?v=PD3YnPSHC-c&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=7)

![query.png](../crm/static/images/querry.png)

- We work from an interactive console accesed by inputing the command **python3 manage.py shell**
- [Query CheatSheet](./accounts/query_demo.py)

## 8. Rendering Data to Templates | Template Tags

[Link](https://www.youtube.com/watch?v=7a23TbUXfWE&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=8)
- Worked on creating the variables that hold query results in views.py
- Also linked the value of these variables and input them in the respective html files

## 9 & 10. Dynamic URL Routing & Templates

[9 - Link](https://www.youtube.com/watch?v=HhjnQIpXqPc&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=9) <br>
[10 - Link](https://www.youtube.com/watch?v=HsyPaQ_B8kY&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=10)

- We worked on the urls.py files as well as updating the href links for a tags across the templates and the
- <str:pk> : **str**ing : **p**rimary **k**ey 

## 11. Create Update & Delete (CRUD) with Model Forms
 
[Link](https://www.youtube.com/watch?v=EX6Tt-ZW0so&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO)

- {% csrf_token %} is a way of passing our data securely
- Note the update and delte order forms in templates and views.py

## 12. Inline Formsets
 
[Link](https://www.youtube.com/watch?v=MRWFg30FmZQ&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=12)

- Inline formsets are used to create multile forms within one form.
- {{ form.management_form }} - sends data for each individual form in the formset.

## 13. Filter Form Table Search

[Link](https://www.youtube.com/watch?v=G-Rct7Na0UQ&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=13)

- Reference djngo filter package
- icontains means be case insensitive in the filter

## 14. User Registration and Login Authentication

[Link](https://www.youtube.com/watch?v=tUqUdu0Sjyc&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO&index=14)

- Would be wise to create an auth_view.py for auth view functions

## 15. User Role Based Permissions & Authentication

[Link](https://www.youtube.com/watch?v=eBsc65jTKvw&list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO)

- 

---

## References
- [Full Youtube Playlist](https://www.youtube.com/playlist?list=PL-51WBLyFTg2vW-_6XBoUpE7vpmoR3ztO)
- [Django QuerySet API Reference](https://docs.djangoproject.com/en/4.1/ref/models/querysets/)
- [Django URl Dispatcher API Reference](https://docs.djangoproject.com/en/4.1/topics/http/urls/)
- [Django Filter Package](https://django-filter.readthedocs.io/en/stable/)
- [Django Flash Messages API](https://docs.djangoproject.com/en/3.0/ref/contrib/messages/#using-messages-in-views-and-templates)
- [Django CORS Headers](https://pypi.org/project/django-cors-headers/)
