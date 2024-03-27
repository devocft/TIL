# Create *forms* from *models*

In a database-driven app, forms map closely to Django models
```python
# articles/models.py
from django.db import models


class Article(models.Model):
    pub_date = models.DateField(auto_now=True)
    headline = models.TextField()
    content = models.TextField()
    reporter = models.TextField()
```

```python
# articles/forms.py
from django import forms
from .models import Article


class ArticleForm(forms.ModelForm):
    class Meta:
        model = Article
        fields = ['headline', 'content', 'reporter']
```

In the shell,
```python
from articles.forms import ArticleForm
a = Article(headline='ModelForm', content='Creating forms from models', reporter='django')
a.save()

# Create a form to add an article
form = ArticleForm()

# Create a form to change an existing article
article = Article.objects.get(pk=1)
form = ArticleForm(instance=article)
```

[source](https://docs.djangoproject.com/en/5.0/topics/forms/modelforms/#modelform)