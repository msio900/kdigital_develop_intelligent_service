# 0705

## 1. 장고 세팅(파이참)





django-admin startproject config .

python manage.py startapp p1

settings

스마트폰 접속

```python
ALLOWED_HOSTS = ['*']# 추가

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'p1',# 추가
]

ROOT_URLCONF = 'config.urls'

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'DIRS': [os.path.join(BASE_DIR, 'templates')],# 추가
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


STATIC_URL = '/static/'
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'static')# 추가
]
DATA_DIRS = [
    os.path.join(BASE_DIR, 'data')# 추가
]
# 임포트 os
```

urls

```python
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('p1.urls')),# 추가
]
임포트 장고
```

p1에 urls 복붙

```python
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.home, name='home'), # 추가 후 views 임포트
]
```

views

```python
def home(request):
    return render(request, 'home.html')
```

template에 home.html 생성

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <h1>Main Page</h1>
</body>
</html>
```

python manage.py migrate



python manage.py runserver 80



## 2. 로거 세팅

settings.py

```python
LOG_FILE = os.path.join(BASE_DIR,'data/mylog.csv');

LOGGING = {
    'version': 1,
    # 기존의 로깅 설정을 비활성화 할 것인가?
    'disable_existing_loggers': False,
    # 포맷터
    # 로그 레코드는 최종적으로 텍스트로 표현됨
    # 이 텍스트의 포맷 형식 정의
    # 여러 포맷 정의 가능
    'formatters': {
        'format1': {
            'format': '[%(asctime)s] %(levelname)s [%(name)s:%(lineno)s] %(message)s',
            'datefmt': '%d/%b/%Y %H:%M:%S'
        },
        'format2': {
            'format': '%(levelname)s %(message)s'
        },
    },
    # 핸들러
    # 로그 레코드로 무슨 작업을 할 것인지 정의
    # 여러 핸들러 정의 가능
    'handlers': {
        # 로그 파일을 만들어 텍스트로 로그레코드 저장
        'file': {
            'level': 'DEBUG',
            'class': 'logging.FileHandler',
            'filename': LOG_FILE,
            'formatter': 'format1',
        },
        # 콘솔(터미널)에 출력
    'console': {
        'level': 'DEBUG',
        'class': 'logging.StreamHandler',
        'formatter': 'format2',
    }
    },
    # 로거
    # 로그 레코드 저장소
    # 로거를 이름별로 정의
    'loggers': {    
        'users': {
            'handlers': ['file'],
            'level': 'DEBUG',
        },
        'items': {
            'handlers': ['console'],
            'level': 'DEBUG',
        }
    },
}
```



2. view.py에 logger 적용

```python
logger = logging.getLogger(**'users'**);

logger.debug(**'user id:'**+id)
```



클래스 만들고 함수 만들고

데이터를 던져라!