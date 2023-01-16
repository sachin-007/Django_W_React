create django project 
create react app : "npx create-react-app <appname>"
drag react app into root directory of django project 
configure TEMPLATES engine
configure URL path
configure static files
cd into react app run "npm run build"





django-admin startproject todo
cd todo
python manage.py runserver

create react app
npx create-react-app reactapp
cd reactapp
npm run build











1st go into django TEMPLATES directory
todo/setting.py
import os

ad this line in templates
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [
            os.path.join(BASE_DIR, 'reactapp/build')
],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

2nd urls.py
Add this lines in 

from django.views.generic import TemplateView

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', TemplateView.as_view(template_name='index.html')),
]


3rd in setting.py 
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'reactapp/build/static')
]


> cd todo
> python manage.py runserver

>cd ..
>cd reactapp
    //  >npm install
>npm run build