# Make Queries

Define a class that inherits the models.Model class in `models.py` of `blog app`
```python
from django.db import models

class Blog(models.Model):
    name = models.CharField(max_length=100)
    tagline = models.TextField()

    def __str__(self):
        return self.name
```


Need to add `app` to `INSTALLED_APPS` in `project/settings.py`
```python
INSTALLED_APPS = [
    'blog.apps.BlogConfig',
    ...
]
```

Execute `shell`
```shell
python manage.py shell
```

Create `object`
```python
from blog.models import Blog

b = Blog(name="Beatles Blog", tagline="All the latest Beatles news.")
b.save()
```

An error occurs if migration is not performed
```
OperationalError: no such table: blog_blog
```
```shell
python manage.py makemigrations
python manage.py migrate
```

[source](
https://docs.djangoproject.com/en/5.0/topics/db/queries/)