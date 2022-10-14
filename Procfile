release: python manage.py migrate
web: daphne chatty.asgi:application --port $PORT --bind 0.0.0.0 -v2
celery: celery -A chatty.celery worker -l info
celerybeat: celery -A chatty beat -l INFO 
celeryworker2: celery -A chatty.celery worker & celery -A chatty beat -l INFO & wait -n
