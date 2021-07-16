
# django_full
django + dash + djangoREST


criar ambiente do projeto
conda create --name djangofull python=3.6

django-admin startproject djangofull .

python manage.py startapp djangofull

baixar o template

setar arquivos estaticos

python manage.py collectstatic

montar o template


asdffdsf

pip install django_plotly_dash

installed apps
'django_plotly_dash.apps.DjangoPlotlyDashConfig',

urls global
path('django_plotly_dash/', include('django_plotly_dash.urls')),


pip install channels daphne redis django-redis channels-redis



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

em settings

CRISPY_TEMPLATE_PACK = 'bootstrap4'

ASGI_APPLICATION = 'djangofull.routing.application'

criar um arquivo routing.py em djangofull

    from channels.routing import ProtocolTypeRouter


CHANNEL_LAYERS= {
    'defaults': {
        'BACKEND': 'channels_redis.core.RedisChannelLayer',
        'CONFIG':{
            'hosts':[('127.0.0.1', 6379,),]

        }

    }
}



STATICFILES_FINDERS = [
    'django.contrib.staticfiles.finders.FileSystemFinder',
    'django.contrib.staticfiles.finders.AppDirectoriesFinder',
    'django.plotly_dash,finders.DashAssetFinder',
    'django.plotly_dash,finders.DashComponentsFinder',
]




configurar o template 

confugurar urls


configurar o base.




fazer migartion


