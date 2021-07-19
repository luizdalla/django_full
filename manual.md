
# django_full =  django + dash + djangoREST

# Quick start guide

1) Criar o ambiente do projeto

`conda create --name djangofull python=3.6`

2) Criar o Projeto Django convencional

`django-admin startproject djangofull . `

`python manage.py startapp djangofull`

3) Baixar o template

https://startbootstrap.com/template/sb-admin

4) Setar arquivos estaticos

`python manage.py collectstatic`

5) Instalar django_plotly_dash

`pip install django_plotly_dash`

6) Configuracoes

installe apps

`'django_plotly_dash.apps.DjangoPlotlyDashConfig'`

urls global

`path('django_plotly_dash/', include('django_plotly_dash.urls'))`

7) Instalar redis

`pip install channels daphne redis django-redis channels-redis`

8) Config Installed Apps

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'home.apps.HomeConfig',
    'django_plotly_dash.apps.DjangoPlotlyDashConfig',
    'channels',
    'channels_redis',
]
```
9) Acrescentar em Settings

```
CRISPY_TEMPLATE_PACK = 'bootstrap4'

ASGI_APPLICATION = 'djangofull.routing.application'
```
10) Criar um arquivo routing.py em djangofull

`from channels.routing import ProtocolTypeRouter`

11) Setar channel layers

```
CHANNEL_LAYERS= {
    'defaults': {
        'BACKEND': 'channels_redis.core.RedisChannelLayer',
        'CONFIG':{
            'hosts':[('127.0.0.1', 6379,),]

        }

    }
}
```

12) Configurar STATIC

```
STATICFILES_FINDERS = [
    'django.contrib.staticfiles.finders.FileSystemFinder',
    'django.contrib.staticfiles.finders.AppDirectoriesFinder',
    'django.plotly_dash,finders.DashAssetFinder',
    'django.plotly_dash,finders.DashComponentsFinder',
]
```

13) Adicionar app dash

14) continua  ...

teminar