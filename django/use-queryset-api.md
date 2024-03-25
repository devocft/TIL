# Use QuerySet API

Install libraries
```shell
pip install ipython
pip install django-extensions
```

**_Include library_**
```python
# settings.py

INSTALLED_APPS = [
    ...
    'django_extensions',
    ...
]
```

Execute shell
```
python manage.py shell_plus
```

Create
```python
c = Blog()
c
"""
<Blog: >
"""

c.name = "Nice View Blog"
c
"""
<Blog: Nice View Blog>
"""

Blog.objects.all()
"""
<QuerySet [<Blog: Beatles Blog>]>
"""

c.save()
Blog.objects.all()
"""
<QuerySet [<Blog: Beatles Blog>, <Blog: Nice View Blog>]>
"""
```

Read
```python
# all
Blog.objects.all()
"""
<QuerySet [<Blog: Beatles Blog>, <Blog: Nice View Blog>]>
"""

# filter
Blog.objects.filter(name__contains="Blog")
"""
<QuerySet [<Blog: Beatles Blog>, <Blog: Nice View Blog>]>
"""
Blog.objects.filter(name__contains="Beatles")
<QuerySet [<Blog: Beatles Blog>]>

# get
Blog.objects.get(pk=1)
"""
<Blog: Beatles Blog>
"""
Blog.objects.get(name="Nice View Blog")
"""
<Blog: Nice View Blog>
"""

# error - get
Blog.objects.get(name="Nice")
"""
DoesNotExist: Blog matching query does not exist.
"""

Blog.objects.get(name__contains="Blog")
"""
MultipleObjectsReturned: get() returned more than one Blog -- it returned 2!
"""
```

Update
```python
u = Blog.objects.get(pk=1)
u
"""
<Blog: Beatles Blog>
"""
u.name = "Coldplay Blog"
u.save()
u
"""
<Blog: Coldplay Blog>
"""
```

Delete
```python
d = Blog.objects.get(pk=1)
d
"""
<Blog: Coldplay Blog>
"""
d.delete()
"""
(1, {'blog.Blog': 1})
"""
Blog.objects.all()
"""
<QuerySet [<Blog: Nice View Blog>]>
"""
```
