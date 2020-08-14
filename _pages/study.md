---
title: "Powerticket's Studying"
permalink: /study/
layout: single

---

[TOC]

***



# Studying

> Fast and steady win the race.
>



## Python

1. [Python basic](study/python-basic.md)



## Django

### Introduction

![img](https://mdn.mozillademos.org/files/13931/basic-django.png)



### Convention

#### Import

1. standard libarary

2. 3rd party

3. django

4. local django

#### App

1. local apps

2. 3rd party apps

3. django apps



### Django Template Language([DTL](https://docs.djangoproject.com/en/3.1/ref/templates/language/))

- Built-in template system for django.
- 조건, 반복, 치환, 필터, 변수 등의 기능을 제공
- For Presentation, not for programming.
- Not run as python codes.



#### Syntax

- variables: `{{ }}`
- filters: `{{ variable|filter }}`
- tags: `{% tag %}`



### Installation

$ `pip install django`



### Start project

$ `django-admin startproject project_name`



### Make app

$ `python manage.py startapp app_name_s`



### Settings

Add app names at `INSTALLED_APPS` list.



### Edit app

`project_name/urls.py` -> `app_name_s/views.py` -> `templates/page_name.html`



### Run

$ `python manage.py runserver`





## C



